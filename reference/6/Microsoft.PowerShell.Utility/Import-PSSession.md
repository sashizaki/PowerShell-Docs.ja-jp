---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PSSession
ms.openlocfilehash: ef5bf676e261e7a4267980a3e87753724ca9bf42
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214971"
---
# <span data-ttu-id="09c91-103">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="09c91-103">Import-PSSession</span></span>

## <span data-ttu-id="09c91-104">概要</span><span class="sxs-lookup"><span data-stu-id="09c91-104">SYNOPSIS</span></span>
<span data-ttu-id="09c91-105">別のセッションから現在のセッションにコマンドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="09c91-105">Imports commands from another session into the current session.</span></span>

## <span data-ttu-id="09c91-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="09c91-106">SYNTAX</span></span>

```
Import-PSSession [-Prefix <String>] [-DisableNameChecking] [[-CommandName] <String[]>] [-AllowClobber]
 [-ArgumentList <Object[]>] [-CommandType <CommandTypes>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-FormatTypeName] <String[]>]
 [-Certificate <X509Certificate2>] [-Session] <PSSession> [<CommonParameters>]
```

## <span data-ttu-id="09c91-107">Description</span><span class="sxs-lookup"><span data-stu-id="09c91-107">DESCRIPTION</span></span>

<span data-ttu-id="09c91-108">**インポート pssession** コマンドレットは、コマンドレット、関数、エイリアスなどのコマンドを、ローカルコンピューターまたはリモートコンピューター上の PSSession から現在のセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="09c91-108">The **Import-PSSession** cmdlet imports commands , such as cmdlets, functions, and aliases, from a PSSession on a local or remote computer into the current session.</span></span>
<span data-ttu-id="09c91-109">Get-Command コマンドレットが PSSession で検索できる任意のコマンドをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="09c91-109">You can import any command that the Get-Command cmdlet can find in the PSSession.</span></span>

<span data-ttu-id="09c91-110">Microsoft Exchange Server シェルなどのカスタマイズされたシェルから、または現在のセッションに含まれていない PowerShell モジュールやスナップインなどの要素を含むセッションからコマンドをインポートするには、 **インポート-PSSession** コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="09c91-110">Use an **Import-PSSession** command to import commands from a customized shell, such as a Microsoft Exchange Server shell, or from a session that includes PowerShell modules and snap-ins or other elements that are not in the current session.</span></span>

<span data-ttu-id="09c91-111">コマンドをインポートするには、最初に New-PSSession コマンドレットを使用して PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="09c91-111">To import commands, first use the New-PSSession cmdlet to create a PSSession.</span></span>
<span data-ttu-id="09c91-112">次に、 **Import-PSSession** コマンドレットを使用して、コマンドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="09c91-112">Then, use the **Import-PSSession** cmdlet to import the commands.</span></span>
<span data-ttu-id="09c91-113">既定では、 **Import-PSSession** は、現在のセッションのコマンドと同じ名前のコマンドを除くすべてのコマンドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="09c91-113">By default, **Import-PSSession** imports all commands except for commands that have the same names as commands in the current session.</span></span>
<span data-ttu-id="09c91-114">すべてのコマンドをインポートするには、 *AllowClobber* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="09c91-114">To import all the commands, use the *AllowClobber* parameter.</span></span>

<span data-ttu-id="09c91-115">インポートしたコマンドは、セッションのコマンドを使用する場合と同じように使用できます。</span><span class="sxs-lookup"><span data-stu-id="09c91-115">You can use imported commands just as you would use any command in the session.</span></span>
<span data-ttu-id="09c91-116">インポートしたコマンドを使用すると、インポートした部分のコマンドがインポート元のセッションで暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="09c91-116">When you use an imported command, the imported part of the command runs implicitly in the session from which it was imported.</span></span>
<span data-ttu-id="09c91-117">ただし、リモート操作は PowerShell によって完全に処理されます。</span><span class="sxs-lookup"><span data-stu-id="09c91-117">However, the remote operations are handled entirely by PowerShell.</span></span>
<span data-ttu-id="09c91-118">リモート操作に注意を払う必要はありませんが、もう一方のセッション (PSSession) への接続を開いたままにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09c91-118">You need not even be aware of them, except that you must keep the connection to the other session (PSSession) open.</span></span>
<span data-ttu-id="09c91-119">接続を閉じると、インポートしたコマンドを利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="09c91-119">If you close it, the imported commands are no longer available.</span></span>

<span data-ttu-id="09c91-120">インポートしたコマンドは、実行時間がローカル コマンドよりも長い場合があるため、 **Import-PSSession** はインポートしたすべてのコマンドに *AsJob* パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="09c91-120">Because imported commands might take longer to run than local commands, **Import-PSSession** adds an *AsJob* parameter to every imported command.</span></span>
<span data-ttu-id="09c91-121">このパラメーターを使用すると、コマンドを PowerShell バックグラウンドジョブとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="09c91-121">This parameter allows you to run the command as a PowerShell background job.</span></span>
<span data-ttu-id="09c91-122">詳細については、「about_Jobs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09c91-122">For more information, see about_Jobs.</span></span>

<span data-ttu-id="09c91-123">**Import-PSSession** を使用すると、PowerShell はインポートされたコマンドをセッションにのみ存在する一時モジュールに追加し、モジュールを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="09c91-123">When you use **Import-PSSession** , PowerShell adds the imported commands to a temporary module that exists only in your session and returns an object that represents the module.</span></span>
<span data-ttu-id="09c91-124">今後のセッションで使用できる永続的なモジュールを作成するには、Export-PSSession コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="09c91-124">To create a persistent module that you can use in future sessions, use the Export-PSSession cmdlet.</span></span>

<span data-ttu-id="09c91-125">**インポート PSSession** コマンドレットは、PowerShell の暗黙的なリモート処理機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="09c91-125">The **Import-PSSession** cmdlet uses the implicit remoting feature of PowerShell.</span></span>
<span data-ttu-id="09c91-126">現在のセッションにコマンドをインポートすると、元のセッションまたは元のコンピューターの同様のセッションで、コマンドが暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="09c91-126">When you import commands into the current session, they run implicitly in the original session or in a similar session on the originating computer.</span></span>

<span data-ttu-id="09c91-127">Windows PowerShell 3.0 以降では、Import-Module コマンドレットを使用して、リモートセッションから現在のセッションにモジュールをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="09c91-127">Beginning in Windows PowerShell 3.0, you can use the Import-Module cmdlet to import modules from a remote session into the current session.</span></span>
<span data-ttu-id="09c91-128">この機能では、暗黙的なリモート処理が使用されます。</span><span class="sxs-lookup"><span data-stu-id="09c91-128">This feature uses implicit remoting.</span></span>
<span data-ttu-id="09c91-129">これは、 **Import-PSSession** を使用してリモート セッションから現在のセッションに選択したモジュールをインポートした場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="09c91-129">It is equivalent to using **Import-PSSession** to import selected modules from a remote session into the current session.</span></span>

## <span data-ttu-id="09c91-130">例</span><span class="sxs-lookup"><span data-stu-id="09c91-130">EXAMPLES</span></span>

### <span data-ttu-id="09c91-131">例 1: PSSession からすべてのコマンドをインポートする</span><span class="sxs-lookup"><span data-stu-id="09c91-131">Example 1: Import all commands from a PSSession</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S
```

<span data-ttu-id="09c91-132">このコマンドは、Server01 コンピューターの PSSession から現在のセッションに、現在のセッションのコマンドと同じ名前のコマンドを除くすべてのコマンドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="09c91-132">This command imports all commands from a PSSession on the Server01 computer into the current session, except for commands that have the same names as commands in the current session.</span></span>

<span data-ttu-id="09c91-133">このコマンドでは *CommandName* パラメーターを使用しないため、インポートされたコマンドに必要な書式データもすべてインポートされます。</span><span class="sxs-lookup"><span data-stu-id="09c91-133">Because this command does not use the *CommandName* parameter, it also imports all of the formatting data required for the imported commands.</span></span>

### <span data-ttu-id="09c91-134">例 2: 特定の文字列で終わるコマンドをインポートする</span><span class="sxs-lookup"><span data-stu-id="09c91-134">Example 2: Import commands that end with a specific string</span></span>

```
PS C:\> $S = New-PSSession https://ps.testlabs.com/powershell
PS C:\> Import-PSSession -Session $S -CommandName *-test -FormatTypeName *
PS C:\> New-Test -Name Test1
PS C:\> Get-Test test1 | Run-Test
```

<span data-ttu-id="09c91-135">これらのコマンドは、PSSession からローカル セッションに名前が "-test" で終わるコマンドをインポートします。その後、インポートしたコマンドレットを使用する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="09c91-135">These commands import the commands with names that end in "-test" from a PSSession into the local session, and then they show how to use an imported cmdlet.</span></span>

<span data-ttu-id="09c91-136">最初のコマンドは、New-PSSession コマンドレットを使用して PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="09c91-136">The first command uses the New-PSSession cmdlet to create a PSSession.</span></span>
<span data-ttu-id="09c91-137">$S 変数に PSSession を保存します。</span><span class="sxs-lookup"><span data-stu-id="09c91-137">It saves the PSSession in the $S variable.</span></span>

<span data-ttu-id="09c91-138">2番目のコマンドは、 **import-pssession** コマンドレットを使用して、$S の pssession から現在のセッションにコマンドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="09c91-138">The second command uses the **Import-PSSession** cmdlet to import commands from the PSSession in $S into the current session.</span></span>
<span data-ttu-id="09c91-139">*CommandName* パラメーターを使用して "Test" という名詞を含むコマンドを指定し、 *FormatTypeName* パラメーターを使用して Test コマンドの書式データをインポートします。</span><span class="sxs-lookup"><span data-stu-id="09c91-139">It uses the *CommandName* parameter to specify commands with the Test noun and the *FormatTypeName* parameter to import the formatting data for the Test commands.</span></span>

<span data-ttu-id="09c91-140">3 番目と 4 番目のコマンドは、現在のセッションでインポートされたコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="09c91-140">The third and fourth commands use the imported commands in the current session.</span></span>
<span data-ttu-id="09c91-141">インポートされたコマンドは、現在のセッションに実際に追加されるため、ローカル構文を使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="09c91-141">Because imported commands are actually added to the current session, you use the local syntax to run them.</span></span>
<span data-ttu-id="09c91-142">Invoke-Command コマンドレットを使用して、インポートしたコマンドを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="09c91-142">You do not need to use the Invoke-Command cmdlet to run an imported command.</span></span>

### <span data-ttu-id="09c91-143">例 3: PSSession からコマンドレットをインポートする</span><span class="sxs-lookup"><span data-stu-id="09c91-143">Example 3: Import cmdlets from a PSSession</span></span>

```
PS C:\> $S1 = New-PSSession -ComputerName s1
PS C:\> $S2 = New-PSSession -ComputerName s2
PS C:\> Import-PSSession -Session s1 -Type cmdlet -Name New-Test, Get-Test -FormatTypeName *
PS C:\> Import-PSSession -Session s2 -Type Cmdlet -Name Set-Test -FormatTypeName *
PS C:\> New-Test Test1 | Set-Test -RunType Full
```

<span data-ttu-id="09c91-144">この例では、ローカルのコマンドレットを使用するのと同じように、インポートされたコマンドレットを使用できることを示します。</span><span class="sxs-lookup"><span data-stu-id="09c91-144">This example shows that you can use imported cmdlets just as you would use local cmdlets.</span></span>

<span data-ttu-id="09c91-145">これらのコマンドは、Server01 コンピューターの PSSession から New-Test コマンドレットと Get-Test コマンドレットをインポートし、Server02 コンピューターの PSSession から Set-Test コマンドレットをインポートします。</span><span class="sxs-lookup"><span data-stu-id="09c91-145">These commands import the New-Test and Get-Test cmdlets from a PSSession on the Server01 computer and the Set-Test cmdlet from a PSSession on the Server02 computer.</span></span>

<span data-ttu-id="09c91-146">別々の PSSession からコマンドレットをインポートした場合でも、パイプを使用して 1 つのコマンドレットから別のコマンドレットにオブジェクトを渡すことができます。エラーにはなりません。</span><span class="sxs-lookup"><span data-stu-id="09c91-146">Even though the cmdlets were imported from different PSSessions, you can pipe an object from one cmdlet to another without error.</span></span>

### <span data-ttu-id="09c91-147">例 4: インポートされたコマンドをバックグラウンドジョブとして実行する</span><span class="sxs-lookup"><span data-stu-id="09c91-147">Example 4: Run an imported command as a background job</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S -CommandName *-test* -FormatTypeName *
PS C:\> $batch = New-Test -Name Batch -AsJob
PS C:\> Receive-Job $batch
```

<span data-ttu-id="09c91-148">この例では、インポートしたコマンドをバックグラウンド ジョブとして実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="09c91-148">This example shows how to run an imported command as a background job.</span></span>

<span data-ttu-id="09c91-149">インポートしたコマンドは、実行時間がローカル コマンドよりも長い場合があるため、 **Import-PSSession** はインポートしたすべてのコマンドに *AsJob* パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="09c91-149">Because imported commands might take longer to run than local commands, **Import-PSSession** adds an *AsJob* parameter to every imported command.</span></span>
<span data-ttu-id="09c91-150">*AsJob* パラメーターを使用すると、コマンドをバックグラウンド ジョブとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="09c91-150">The *AsJob* parameter lets you run the command as a background job.</span></span>

<span data-ttu-id="09c91-151">最初のコマンドは、Server01 コンピューター上に PSSession を作成し、PSSession オブジェクトを $S 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="09c91-151">The first command creates a PSSession on the Server01 computer and saves the PSSession object in the $S variable.</span></span>

<span data-ttu-id="09c91-152">2番目のコマンドは、 **インポート-PSSession** を使用して、$S の PSSession から現在のセッションにテストコマンドレットをインポートします。</span><span class="sxs-lookup"><span data-stu-id="09c91-152">The second command uses **Import-PSSession** to import the Test cmdlets from the PSSession in $S into the current session.</span></span>

<span data-ttu-id="09c91-153">3 番目のコマンドは、インポートした New-Test コマンドレットの *AsJob* パラメーターを使用して、New-Test コマンドをバックグラウンド ジョブとして実行します。</span><span class="sxs-lookup"><span data-stu-id="09c91-153">The third command uses the *AsJob* parameter of the imported New-Test cmdlet to run a New-Test command as a background job.</span></span>
<span data-ttu-id="09c91-154">このコマンドでは、New-Test から返されたジョブ オブジェクトを $batch 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="09c91-154">The command saves the job object that New-Test returns in the $batch variable.</span></span>

<span data-ttu-id="09c91-155">4番目のコマンドは、Receive-Job コマンドレットを使用して、ジョブの結果を $batch 変数に取得します。</span><span class="sxs-lookup"><span data-stu-id="09c91-155">The fourth command uses the Receive-Job cmdlet to get the results of the job in the $batch variable.</span></span>

### <span data-ttu-id="09c91-156">例 5: PowerShell モジュールからコマンドレットと関数をインポートする</span><span class="sxs-lookup"><span data-stu-id="09c91-156">Example 5: Import cmdlets and functions from a PowerShell module</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Invoke-Command -Session $S {Import-Module TestManagement}
PS C:\> Import-PSSession -Session $S -Module TestManagement
```

<span data-ttu-id="09c91-157">この例では、リモートコンピューターの PowerShell モジュールから現在のセッションにコマンドレットと関数をインポートする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="09c91-157">This example shows how to import the cmdlets and functions from a PowerShell module on a remote computer into the current session.</span></span>

<span data-ttu-id="09c91-158">最初のコマンドは、Server01 コンピューター上に PSSession を作成し、$S 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="09c91-158">The first command creates a PSSession on the Server01 computer and saves it in the $S variable.</span></span>

<span data-ttu-id="09c91-159">2番目のコマンドは、 **コマンド** レットを使用して、$S 内の PSSession で Import-Module コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="09c91-159">The second command uses the **Invoke-Command** cmdlet to run an Import-Module command in the PSSession in $S.</span></span>

<span data-ttu-id="09c91-160">通常、モジュールは、PowerShell プロファイルの [ **モジュールのインポート** ] コマンドによってすべてのセッションに追加されますが、プロファイルは pssessions では実行されません。</span><span class="sxs-lookup"><span data-stu-id="09c91-160">Typically, the module would be added to all sessions by an **Import-Module** command in a PowerShell profile, but profiles are not run in PSSessions.</span></span>

<span data-ttu-id="09c91-161">3番目のコマンドは、 **import-PSSession** の *module* パラメーターを使用して、モジュール内のコマンドレットと関数を現在のセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="09c91-161">The third command uses the *Module*  parameter of **Import-PSSession** to import the cmdlets and functions in the module into the current session.</span></span>

### <span data-ttu-id="09c91-162">例 6: 一時ファイルにモジュールを作成する</span><span class="sxs-lookup"><span data-stu-id="09c91-162">Example 6: Create a module in a temporary file</span></span>

```
PS C:\> Import-PSSession $S -CommandName Get-Date, SearchHelp -FormatTypeName * -AllowClobber

Name              : tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
Path              : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf\tmp_79468106-4e1d-4d90-af97-1154f9317239_
tcw1zunz.ttf.psm1
Description       : Implicit remoting for http://server01.corp.fabrikam.com/wsman
Guid              : 79468106-4e1d-4d90-af97-1154f9317239
Version           : 1.0
ModuleBase        : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
ModuleType        : Script
PrivateData       : {ImplicitRemoting}
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Get-Date, Get-Date], [SearchHelp, SearchHelp]}
ExportedVariables : {}
NestedModules     : {}
```

<span data-ttu-id="09c91-163">この例では、 **Import-PSSession** でディスク上の一時ファイルにモジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="09c91-163">This example shows that **Import-PSSession** creates a module in a temporary file on disk.</span></span>
<span data-ttu-id="09c91-164">また、現在のセッションにインポートする前に、すべてのコマンドを関数に変換します。</span><span class="sxs-lookup"><span data-stu-id="09c91-164">It also shows that all commands are converted into functions before they are imported into the current session.</span></span>

<span data-ttu-id="09c91-165">このコマンドは、Get-Date コマンドレットと SearchHelp 関数を現在のセッションにインポートするために、 **import-PSSession** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="09c91-165">The command uses the **Import-PSSession** cmdlet to import a Get-Date cmdlet and a SearchHelp function into the current session.</span></span>

<span data-ttu-id="09c91-166">**Import-PSSession** コマンドレットは、一時的なモジュールを表す **PSModuleInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="09c91-166">The **Import-PSSession** cmdlet returns a **PSModuleInfo** object that represents the temporary module.</span></span>
<span data-ttu-id="09c91-167">**Path** プロパティの値は、 **Import-PSSession** によって、一時的な場所にスクリプト モジュール (.psm1) ファイルが作成されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="09c91-167">The value of the **Path** property shows that **Import-PSSession** created a script module (.psm1) file in a temporary location.</span></span>
<span data-ttu-id="09c91-168">**ExportedFunctions** プロパティは、 **Get-Date** コマンドレットと SearchHelp 関数が両方とも関数としてインポートされたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="09c91-168">The **ExportedFunctions** property shows that the **Get-Date** cmdlet and the SearchHelp function were both imported as functions.</span></span>

### <span data-ttu-id="09c91-169">例 7: インポートされたコマンドによって非表示になっているコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="09c91-169">Example 7: Run a command that is hidden by an imported command</span></span>

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

<span data-ttu-id="09c91-170">この例では、インポートされたコマンドによって非表示になったコマンドを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="09c91-170">This example shows how to run a command that is hidden by an imported command.</span></span>

<span data-ttu-id="09c91-171">最初のコマンドは、$S 変数の PSSession から Get-Date コマンドレットをインポートします。</span><span class="sxs-lookup"><span data-stu-id="09c91-171">The first command imports a Get-Date cmdlet from the PSSession in the $S variable.</span></span>
<span data-ttu-id="09c91-172">現在のセッションには **Get-Date** コマンドレットが含まれているため、このコマンドには *AllowClobber* パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="09c91-172">Because the current session includes a **Get-Date** cmdlet, the *AllowClobber* parameter is required in the command.</span></span>

<span data-ttu-id="09c91-173">2番目のコマンドは、Get-Command コマンドレットの **all** パラメーターを使用して、現在のセッションのすべての **get Date** コマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="09c91-173">The second command uses the **All** parameter of the Get-Command cmdlet to get all **Get-Date** commands in the current session.</span></span>
<span data-ttu-id="09c91-174">出力には、セッションに元の **Get-Date** コマンドレットと **Get-Date** 関数が含まれていることが示されています。</span><span class="sxs-lookup"><span data-stu-id="09c91-174">The output shows that the session includes the original **Get-Date** cmdlet and a **Get-Date** function.</span></span>
<span data-ttu-id="09c91-175">**Get date** 関数は、$S の PSSession でインポートされた **get date** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="09c91-175">The **Get-Date** function runs the imported **Get-Date** cmdlet in the PSSession in $S.</span></span>

<span data-ttu-id="09c91-176">3 番目のコマンドは、 **Get-Date** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="09c91-176">The third command runs a **Get-Date** command.</span></span>
<span data-ttu-id="09c91-177">関数はコマンドレットよりも優先されるため、PowerShell はインポートされた **Get Date** 関数を実行します。この関数は、ユリウス暦の日付を返します。</span><span class="sxs-lookup"><span data-stu-id="09c91-177">Because functions take precedence over cmdlets, PowerShell runs the imported **Get-Date** function, which returns a Julian date.</span></span>

<span data-ttu-id="09c91-178">4 番目と 5 番目のコマンドは、修飾名を使用して、インポートされたコマンドによって非表示になったコマンドを実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="09c91-178">The fourth and fifth commands show how to use a qualified name to run a command that is hidden by an imported command.</span></span>

<span data-ttu-id="09c91-179">4番目のコマンドは、元の **Get Date** コマンドレットを現在のセッションに追加した PowerShell スナップインの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="09c91-179">The fourth command gets the name of the PowerShell snap-in that added the original **Get-Date** cmdlet to the current session.</span></span>

<span data-ttu-id="09c91-180">5 番目のコマンドは、スナップインで修飾された **Get-Date** コマンドレットの名前を使用して、 **Get-Date** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="09c91-180">The fifth command uses the snap-in-qualified name of the **Get-Date** cmdlet to run a **Get-Date** command.</span></span>

<span data-ttu-id="09c91-181">コマンドの優先順位と非表示のコマンドの詳細については、「about_Command_Precedence」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09c91-181">For more information about command precedence and hidden commands, see about_Command_Precedence.</span></span>

### <span data-ttu-id="09c91-182">例 8: 名前に特定の文字列が含まれているコマンドをインポートする</span><span class="sxs-lookup"><span data-stu-id="09c91-182">Example 8: Import commands that have a specific string in their names</span></span>

```
PS C:\> Import-PSSession -Session $S -CommandName *Item* -AllowClobber
```

<span data-ttu-id="09c91-183">このコマンドは、$S の PSSession からの項目を含む名前を持つコマンドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="09c91-183">This command imports commands whose names include Item from the PSSession in $S.</span></span>
<span data-ttu-id="09c91-184">このコマンドには、 *CommandName* パラメーターは含まれていますが、 *formattypedata* パラメーターは含まれていないため、コマンドのみがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="09c91-184">Because the command includes the *CommandName* parameter but not the *FormatTypeData* parameter, only the command is imported.</span></span>

<span data-ttu-id="09c91-185">このコマンドは、現在のセッションにコマンドの書式データが既に存在しており、 **Import-PSSession** を使用してリモート コンピューターでそのコマンドを実行する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="09c91-185">Use this command when you are using **Import-PSSession** to run a command on a remote computer and you already have the formatting data for the command in the current session.</span></span>

### <span data-ttu-id="09c91-186">例 9: モジュールパラメーターを使用して、セッションにインポートされたコマンドを検出する</span><span class="sxs-lookup"><span data-stu-id="09c91-186">Example 9: Use the Module parameter to discover which commands were imported into the session</span></span>

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

<span data-ttu-id="09c91-187">このコマンドは、 **Get コマンド** の *Module* パラメーターを使用して、 **Import-PSSession** コマンドによってセッションにインポートされたコマンドを確認する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="09c91-187">This command shows how to use the *Module* parameter of **Get-Command** to find out which commands were imported into the session by an **Import-PSSession** command.</span></span>

<span data-ttu-id="09c91-188">最初のコマンドは、 **import-pssession** コマンドレットを使用して、$S 変数の PSSession から "bits" を含む名前のコマンドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="09c91-188">The first command uses the **Import-PSSession** cmdlet to import commands whose names include "bits" from the PSSession in the $S variable.</span></span>
<span data-ttu-id="09c91-189">**Import-PSSession** コマンドは、一時的なモジュールを返し、そのモジュールを $m 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="09c91-189">The **Import-PSSession** command returns a temporary module, and the command saves the module in the $m variable.</span></span>

<span data-ttu-id="09c91-190">2番目のコマンドは、Get-Command コマンドレットを使用して、モジュールによって $M 変数にエクスポートされたコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="09c91-190">The second command uses the Get-Command cmdlet to get the commands that are exported by the module in the $M variable.</span></span>

<span data-ttu-id="09c91-191">*Module* パラメーターは、モジュール名用に設計されており、文字列値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="09c91-191">The *Module* parameter takes a string value, which is designed for the module name.</span></span>
<span data-ttu-id="09c91-192">ただし、モジュールオブジェクトを送信すると、PowerShell はモジュールオブジェクトに対して **ToString** メソッドを使用します。これにより、モジュール名が返されます。</span><span class="sxs-lookup"><span data-stu-id="09c91-192">However, when you submit a module object, PowerShell uses the **ToString** method on the module object, which returns the module name.</span></span>

<span data-ttu-id="09c91-193">**Get command** コマンドは、"" に相当し `Get-Command $M.Name` ます。</span><span class="sxs-lookup"><span data-stu-id="09c91-193">The **Get-Command** command is the equivalent of `Get-Command $M.Name`".</span></span>

## <span data-ttu-id="09c91-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="09c91-194">PARAMETERS</span></span>

### <span data-ttu-id="09c91-195">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="09c91-195">-AllowClobber</span></span>

<span data-ttu-id="09c91-196">このコマンドレットが、現在のセッションのコマンドと同じ名前を持つ場合でも、指定したコマンドをインポートすることを示します。</span><span class="sxs-lookup"><span data-stu-id="09c91-196">Indicates that this cmdlet imports the specified commands, even if they have the same names as commands in the current session.</span></span>

<span data-ttu-id="09c91-197">現在のセッションにあるコマンドと同じ名前のコマンドをインポートする場合、インポートされたコマンドを非表示にするか、元のコマンドを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="09c91-197">If you import a command with the same name as a command in the current session, the imported command hides or replaces the original commands.</span></span>
<span data-ttu-id="09c91-198">詳細については、「about_Command_Precedence」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09c91-198">For more information, see about_Command_Precedence.</span></span>

<span data-ttu-id="09c91-199">既定では、 **Import-PSSession** は、現在のセッションのコマンドと同じ名前のコマンドをインポートしません。</span><span class="sxs-lookup"><span data-stu-id="09c91-199">By default, **Import-PSSession** does not import commands that have the same name as commands in the current session.</span></span>

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

### <span data-ttu-id="09c91-200">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="09c91-200">-ArgumentList</span></span>

<span data-ttu-id="09c91-201">指定された引数 (パラメーター値) を使用した結果として得られるコマンドの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="09c91-201">Specifies an array of commands that results from using the specified arguments (parameter values).</span></span>

<span data-ttu-id="09c91-202">たとえば、証明書 (Cert:) の Get-Item コマンドのバリアントをインポートするには、$S の PSSession のドライブに、「」と入力 `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:` します。</span><span class="sxs-lookup"><span data-stu-id="09c91-202">For instance, to import the variant of the Get-Item command in the certificate (Cert:) drive in the PSSession in $S, type `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:`.</span></span>

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

### <span data-ttu-id="09c91-203">-証明書</span><span class="sxs-lookup"><span data-stu-id="09c91-203">-Certificate</span></span>

<span data-ttu-id="09c91-204">**Import-PSSession** によって作成された一時的なモジュールの書式ファイル (\*Format.ps1xml) またはスクリプト モジュール ファイル (.psm1) の署名に使用するクライアント証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="09c91-204">Specifies the client certificate that is used to sign the format files (\*.Format.ps1xml) or script module files (.psm1) in the temporary module that **Import-PSSession** creates.</span></span>

<span data-ttu-id="09c91-205">証明書が格納されている変数を入力するか、証明書を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="09c91-205">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="09c91-206">証明書を検索するには、Get-PfxCertificate コマンドレットを使用するか、証明書 (Cert:) で Get-ChildItem コマンドレットを使用します。駆動.</span><span class="sxs-lookup"><span data-stu-id="09c91-206">To find a certificate, use the Get-PfxCertificate cmdlet or use the Get-ChildItem cmdlet in the Certificate (Cert:) drive.</span></span>
<span data-ttu-id="09c91-207">証明書が無効な場合、または証明書に十分な権限がない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="09c91-207">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="09c91-208">-CommandName</span><span class="sxs-lookup"><span data-stu-id="09c91-208">-CommandName</span></span>

<span data-ttu-id="09c91-209">指定された名前または名前パターンのコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="09c91-209">Specifies commands with the specified names or name patterns.</span></span>
<span data-ttu-id="09c91-210">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="09c91-210">Wildcards are permitted.</span></span>
<span data-ttu-id="09c91-211">*CommandName* またはそのエイリアスである *Name* を使用します。</span><span class="sxs-lookup"><span data-stu-id="09c91-211">Use *CommandName* or its alias, *Name* .</span></span>

<span data-ttu-id="09c91-212">既定では、 **Import-PSSession** は、現在のセッションのコマンドと同じ名前のコマンドを除いて、セッションのすべてのコマンドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="09c91-212">By default, **Import-PSSession** imports all commands from the session, except for commands that have the same names as commands in the current session.</span></span>
<span data-ttu-id="09c91-213">そのため、インポート先のセッションでインポートしたコマンドが非表示になることや、置き換えられることがありません。</span><span class="sxs-lookup"><span data-stu-id="09c91-213">This prevents imported commands from hiding or replacing commands in the session.</span></span>
<span data-ttu-id="09c91-214">非表示になったり、他のコマンドを置き換えたりするコマンドを含め、すべてのコマンドをインポートするには、 *AllowClobber* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="09c91-214">To import all commands, even those that hide or replace other commands, use the *AllowClobber* parameter.</span></span>

<span data-ttu-id="09c91-215">*CommandName* パラメーターを使用する場合は、 *FormatTypeName* パラメーターを使用しない限り、コマンドの書式ファイルはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="09c91-215">If you use the *CommandName* parameter, the formatting files for the commands are not imported unless you use the *FormatTypeName* parameter.</span></span>
<span data-ttu-id="09c91-216">同様に、 *FormatTypeName* パラメーターを使用する場合は、 *CommandName* パラメーターを使用しない限り、コマンドはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="09c91-216">Similarly, if you use the *FormatTypeName* parameter, no commands are imported unless you use the *CommandName* parameter.</span></span>

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

### <span data-ttu-id="09c91-217">-CommandType</span><span class="sxs-lookup"><span data-stu-id="09c91-217">-CommandType</span></span>

<span data-ttu-id="09c91-218">コマンドオブジェクトの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="09c91-218">Specifies the type of command objects.</span></span>
<span data-ttu-id="09c91-219">既定値は Cmdlet です。</span><span class="sxs-lookup"><span data-stu-id="09c91-219">The default value is Cmdlet.</span></span>
<span data-ttu-id="09c91-220">*CommandType* またはそのエイリアスの *Type* を使用します。</span><span class="sxs-lookup"><span data-stu-id="09c91-220">Use *CommandType* or its alias, *Type* .</span></span>
<span data-ttu-id="09c91-221">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="09c91-221">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="09c91-222">エイリアス.</span><span class="sxs-lookup"><span data-stu-id="09c91-222">Alias.</span></span>
<span data-ttu-id="09c91-223">リモートセッションの PowerShell エイリアス。</span><span class="sxs-lookup"><span data-stu-id="09c91-223">The PowerShell aliases in the remote session.</span></span>
- <span data-ttu-id="09c91-224">すべて。</span><span class="sxs-lookup"><span data-stu-id="09c91-224">All.</span></span>
<span data-ttu-id="09c91-225">リモート セッションのコマンドレットと関数。</span><span class="sxs-lookup"><span data-stu-id="09c91-225">The cmdlets and functions in the remote session.</span></span>
- <span data-ttu-id="09c91-226">アプリケーション をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09c91-226">Application.</span></span>
<span data-ttu-id="09c91-227">リモートセッションの Path 環境変数 ($env:p a) に一覧表示されているパス内の PowerShell ファイル以外のすべてのファイル (.txt、.exe、.dll ファイルなど)。</span><span class="sxs-lookup"><span data-stu-id="09c91-227">All the files other than PowerShell files in the paths that are listed in the Path environment variable ($env:path) in the remote session, including .txt, .exe, and .dll files.</span></span>
- <span data-ttu-id="09c91-228">コマンドレット.</span><span class="sxs-lookup"><span data-stu-id="09c91-228">Cmdlet.</span></span>
<span data-ttu-id="09c91-229">リモート セッションのコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="09c91-229">The cmdlets in the remote session.</span></span>
<span data-ttu-id="09c91-230">"Cmdlet" が既定値です。</span><span class="sxs-lookup"><span data-stu-id="09c91-230">"Cmdlet" is the default.</span></span>
- <span data-ttu-id="09c91-231">ExternalScript。</span><span class="sxs-lookup"><span data-stu-id="09c91-231">ExternalScript.</span></span>
<span data-ttu-id="09c91-232">リモート セッションの Path 環境変数 ($env:path) に格納されているパスにある .ps1 ファイル。</span><span class="sxs-lookup"><span data-stu-id="09c91-232">The .ps1 files in the paths listed in the Path environment variable ($env:path) in the remote session.</span></span>
- <span data-ttu-id="09c91-233">フィルターと関数。</span><span class="sxs-lookup"><span data-stu-id="09c91-233">Filter and Function.</span></span>
<span data-ttu-id="09c91-234">リモートセッションの PowerShell 関数。</span><span class="sxs-lookup"><span data-stu-id="09c91-234">The PowerShell functions in the remote session.</span></span>
- <span data-ttu-id="09c91-235">スクリプティング。</span><span class="sxs-lookup"><span data-stu-id="09c91-235">Script.</span></span>
<span data-ttu-id="09c91-236">リモート セッションのスクリプト ブロック。</span><span class="sxs-lookup"><span data-stu-id="09c91-236">The script blocks in the remote session.</span></span>

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

### <span data-ttu-id="09c91-237">-DisableNameChecking</span><span class="sxs-lookup"><span data-stu-id="09c91-237">-DisableNameChecking</span></span>

<span data-ttu-id="09c91-238">このコマンドレットが、許可されていない動詞または禁止された文字を含んでいる名前を持つコマンドレットまたは関数をインポートしたときに警告するメッセージを抑制することを示します。</span><span class="sxs-lookup"><span data-stu-id="09c91-238">Indicates that this cmdlet suppresses the message that warns you when you import a cmdlet or function whose name includes an unapproved verb or a prohibited character.</span></span>

<span data-ttu-id="09c91-239">既定では、インポートしたモジュールによって、名前に許可されていない動詞を持つコマンドレットまたは関数がエクスポートされると、PowerShell によって次の警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09c91-239">By default, when a module that you import exports cmdlets or functions that have unapproved verbs in their names, the PowerShell displays the following warning message:</span></span>

<span data-ttu-id="09c91-240">"警告: インポートされたコマンド名には、許可されていない動詞が含まれているため、検出できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="09c91-240">"WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span>
<span data-ttu-id="09c91-241">詳細については Verbose パラメーターを使用するか、「Get-Verb」と入力して承認されている動詞の一覧を参照してください。"</span><span class="sxs-lookup"><span data-stu-id="09c91-241">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs."</span></span>

<span data-ttu-id="09c91-242">このメッセージは、単なる警告です。</span><span class="sxs-lookup"><span data-stu-id="09c91-242">This message is only a warning.</span></span>
<span data-ttu-id="09c91-243">実際には、非準拠のコマンドを含む、すべてのモジュールがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="09c91-243">The complete module is still imported, including the non-conforming commands.</span></span>
<span data-ttu-id="09c91-244">モジュール ユーザーにメッセージが表示されますが、名前付けの問題はモジュール作成者が解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09c91-244">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

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

### <span data-ttu-id="09c91-245">-FormatTypeName</span><span class="sxs-lookup"><span data-stu-id="09c91-245">-FormatTypeName</span></span>

<span data-ttu-id="09c91-246">指定された Microsoft .NET Framework 型の書式設定命令を指定します。</span><span class="sxs-lookup"><span data-stu-id="09c91-246">Specifies formatting instructions for the specified Microsoft .NET Framework types.</span></span>
<span data-ttu-id="09c91-247">型名を入力します。</span><span class="sxs-lookup"><span data-stu-id="09c91-247">Enter the type names.</span></span>
<span data-ttu-id="09c91-248">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="09c91-248">Wildcards are permitted.</span></span>

<span data-ttu-id="09c91-249">このパラメーターの値は、コマンドのインポート元のセッションで Get-FormatData コマンドによって返される型名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="09c91-249">The value of this parameter must be the name of a type that is returned by a Get-FormatData command in the session from which the commands are being imported.</span></span>
<span data-ttu-id="09c91-250">リモート セッション内のすべての書式設定データを取得するには、「\*」を入力します。</span><span class="sxs-lookup"><span data-stu-id="09c91-250">To get all of the formatting data in the remote session, type \*.</span></span>

<span data-ttu-id="09c91-251">コマンドに *CommandName* パラメーターまたは *formattypename* パラメーターのいずれかが含まれていない場合は、リモートセッションで、 **formattypename** コマンドによって返されたすべての .NET Framework 型の書式設定命令が **インポート** されます。</span><span class="sxs-lookup"><span data-stu-id="09c91-251">If the command does not include either the *CommandName* or *FormatTypeName* parameter, **Import-PSSession** imports formatting instructions for all .NET Framework types returned by a **Get-FormatData** command in the remote session.</span></span>

<span data-ttu-id="09c91-252">*FormatTypeName* パラメーターを使用する場合は、 *CommandName* パラメーターを使用しない限り、コマンドはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="09c91-252">If you use the *FormatTypeName* parameter, no commands are imported unless you use the *CommandName* parameter.</span></span>

<span data-ttu-id="09c91-253">同様に、 *CommandName* パラメーターを使用する場合は、 *FormatTypeName* パラメーターを使用しない限り、コマンドの書式ファイルはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="09c91-253">Similarly, if you use the *CommandName* parameter, the formatting files for the commands are not imported unless you use the *FormatTypeName* parameter.</span></span>

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

### <span data-ttu-id="09c91-254">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="09c91-254">-FullyQualifiedModule</span></span>

<span data-ttu-id="09c91-255">**Modulの** 特定のオブジェクトの形式で指定された名前を持つモジュールを指定します (MSDN ライブラリの「 [Modulの注意事項コンストラクター (Hashtable)](https://msdn.microsoft.com/library/jj136290) 」の「解説」で説明しています)。</span><span class="sxs-lookup"><span data-stu-id="09c91-255">Specifies modules with names that are specified in the form of **ModuleSpecification** objects (described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](https://msdn.microsoft.com/library/jj136290) in the MSDN library).</span></span>
<span data-ttu-id="09c91-256">たとえば、 *FullyQualifiedModule* パラメーターは、@ {ModuleName = "ModuleName"; という形式で指定されたモジュール名を受け入れます。ModuleVersion = "version_number"} または @ {ModuleName = "ModuleName";ModuleVersion = "version_number";Guid = "GUID"}。</span><span class="sxs-lookup"><span data-stu-id="09c91-256">For example, the *FullyQualifiedModule* parameter accepts a module name that is specified in the format @{ModuleName = "modulename"; ModuleVersion = "version_number"} or @{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.</span></span>
<span data-ttu-id="09c91-257">**ModuleName** と **ModuleVersion** は必須ですが、 **Guid** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="09c91-257">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="09c91-258">*モジュール* パラメーターと同じコマンドで *FullyQualifiedModule* パラメーターを指定することはできません。2つのパラメーターは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="09c91-258">You cannot specify the *FullyQualifiedModule* parameter in the same command as a *Module* parameter; the two parameters are mutually exclusive.</span></span>

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

### <span data-ttu-id="09c91-259">-モジュール</span><span class="sxs-lookup"><span data-stu-id="09c91-259">-Module</span></span>

<span data-ttu-id="09c91-260">PowerShell スナップインおよびモジュールのコマンドの配列とを指定します。</span><span class="sxs-lookup"><span data-stu-id="09c91-260">Specifies and array of commands in the PowerShell snap-ins and modules.</span></span>
<span data-ttu-id="09c91-261">スナップインとモジュールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="09c91-261">Enter the snap-in and module names.</span></span>
<span data-ttu-id="09c91-262">ワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="09c91-262">Wildcards are not permitted.</span></span>

<span data-ttu-id="09c91-263">**インポート-PSSession** では、スナップインからプロバイダーをインポートできません。</span><span class="sxs-lookup"><span data-stu-id="09c91-263">**Import-PSSession** cannot import providers from a snap-in.</span></span>

<span data-ttu-id="09c91-264">詳細については、「about_PSSnapins」と「[about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09c91-264">For more information, see about_PSSnapins and [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

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

### <span data-ttu-id="09c91-265">-Prefix</span><span class="sxs-lookup"><span data-stu-id="09c91-265">-Prefix</span></span>

<span data-ttu-id="09c91-266">インポートされたコマンドの名前の名詞のプレフィックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="09c91-266">Specifies a prefix to the nouns in the names of imported commands.</span></span>

<span data-ttu-id="09c91-267">セッションに同じ名前の別のコマンドが存在する場合に発生する名前の競合を回避するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="09c91-267">Use this parameter to avoid name conflicts that might occur when different commands in the session have the same name.</span></span>

<span data-ttu-id="09c91-268">たとえば、プレフィックス Remote を指定して Get-Date コマンドレットをインポートした場合、このコマンドレットはセッションでは Get-help Date として認識され、元の **Get date** コマンドレットと混同されることはありません。</span><span class="sxs-lookup"><span data-stu-id="09c91-268">For instance, if you specify the prefix Remote and then import a Get-Date cmdlet, the cmdlet is known in the session as Get-RemoteDate, and it is not confused with the original **Get-Date** cmdlet.</span></span>

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

### <span data-ttu-id="09c91-269">-セッション</span><span class="sxs-lookup"><span data-stu-id="09c91-269">-Session</span></span>

<span data-ttu-id="09c91-270">コマンドレットのインポート元の **PSSession** を指定します。</span><span class="sxs-lookup"><span data-stu-id="09c91-270">Specifies the **PSSession** from which the cmdlets are imported.</span></span>
<span data-ttu-id="09c91-271">セッションオブジェクトを含む変数、または New-PSSession や Get-PSSession コマンドなどのセッションオブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="09c91-271">Enter a variable that contains a session object or a command that gets a session object, such as a New-PSSession or Get-PSSession command.</span></span>
<span data-ttu-id="09c91-272">指定できるセッションは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="09c91-272">You can specify only one session.</span></span>
<span data-ttu-id="09c91-273">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="09c91-273">This parameter is required.</span></span>

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

### <span data-ttu-id="09c91-274">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="09c91-274">CommonParameters</span></span>

<span data-ttu-id="09c91-275">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="09c91-275">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="09c91-276">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09c91-276">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="09c91-277">入力</span><span class="sxs-lookup"><span data-stu-id="09c91-277">INPUTS</span></span>

### <span data-ttu-id="09c91-278">なし</span><span class="sxs-lookup"><span data-stu-id="09c91-278">None</span></span>

<span data-ttu-id="09c91-279">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="09c91-279">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="09c91-280">出力</span><span class="sxs-lookup"><span data-stu-id="09c91-280">OUTPUTS</span></span>

### <span data-ttu-id="09c91-281">PSModuleInfo (システム管理)</span><span class="sxs-lookup"><span data-stu-id="09c91-281">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="09c91-282">**インポート-PSSession** は、New-Module と Get-Module のコマンドレットが返すのと同じモジュールオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="09c91-282">**Import-PSSession** returns the same module object that New-Module and Get-Module cmdlets return.</span></span>
<span data-ttu-id="09c91-283">ただし、インポートされたモジュールは一時的なもので、現在のセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="09c91-283">However, the imported module is temporary and exists only in the current session.</span></span>
<span data-ttu-id="09c91-284">ディスクにパーマネントモジュールを作成するには、Export-PSSession コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="09c91-284">To create a permanent module on disk, use the Export-PSSession cmdlet.</span></span>

## <span data-ttu-id="09c91-285">注</span><span class="sxs-lookup"><span data-stu-id="09c91-285">NOTES</span></span>

* <span data-ttu-id="09c91-286">**インポート-PSSession** は、PowerShell リモート処理インフラストラクチャに依存します。</span><span class="sxs-lookup"><span data-stu-id="09c91-286">**Import-PSSession** relies on the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="09c91-287">このコマンドレットを使用するには、WS-Management リモート処理用にコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09c91-287">To use this cmdlet, the computer must be configured for WS-Management remoting.</span></span> <span data-ttu-id="09c91-288">詳細については、「about_Remote」および「about_Remote_Requirements」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09c91-288">For more information, see about_Remote and about_Remote_Requirements.</span></span>
* <span data-ttu-id="09c91-289">**インポート-PSSession** は、変数または PowerShell プロバイダーをインポートしません。</span><span class="sxs-lookup"><span data-stu-id="09c91-289">**Import-PSSession** does not import variables or PowerShell providers.</span></span>
* <span data-ttu-id="09c91-290">現在のセッションのコマンドと同じ名前のコマンドをインポートすると、インポートされたコマンドによって、現在のセッションのエイリアス、関数、およびコマンドレットが非表示になったり、現在のセッションの関数や変数が置き換えられたりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="09c91-290">When you import commands that have the same names as commands in the current session, the imported commands can hide aliases, functions, and cmdlets in the session and they can replace functions and variables in the session.</span></span> <span data-ttu-id="09c91-291">名前の競合を回避するには、 *Prefix* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="09c91-291">To prevent name conflicts, use the *Prefix* parameter.</span></span> <span data-ttu-id="09c91-292">詳細については、「about_Command_Precedence」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09c91-292">For more information, see about_Command_Precedence.</span></span>
* <span data-ttu-id="09c91-293">**インポート-PSSession** は、すべてのコマンドをインポート前に関数に変換します。</span><span class="sxs-lookup"><span data-stu-id="09c91-293">**Import-PSSession** converts all commands into functions before it imports them.</span></span> <span data-ttu-id="09c91-294">そのため、インポートされたコマンドの動作は、元のコマンドの種類が維持されている場合と少し異なります。</span><span class="sxs-lookup"><span data-stu-id="09c91-294">As a result, imported commands behave a bit differently than they would if they retained their original command type.</span></span> <span data-ttu-id="09c91-295">たとえば、PSSession からコマンドレットをインポートした後、モジュールまたはスナップインから同じ名前のコマンドレットをインポートした場合は、関数はコマンドレットよりも優先されるため、既定では PSSession からインポートしたコマンドレットが常に実行されます。</span><span class="sxs-lookup"><span data-stu-id="09c91-295">For example, if you import a cmdlet from a PSSession and then import a cmdlet with the same name from a module or snap-in, the cmdlet that is imported from the PSSession always runs by default because functions take precedence over cmdlets.</span></span> <span data-ttu-id="09c91-296">また、同じ名前のエイリアスが存在するセッションにエイリアスをインポートした場合は、エイリアスは関数よりも優先されるため、元のエイリアスが常に使用されます。</span><span class="sxs-lookup"><span data-stu-id="09c91-296">Conversely, if you import an alias into a session that has an alias with the same name, the original alias is always used, because aliases take precedence over functions.</span></span> <span data-ttu-id="09c91-297">詳細については、「about_Command_Precedence」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09c91-297">For more information, see about_Command_Precedence.</span></span>
* <span data-ttu-id="09c91-298">Write-Progress コマンドレット **を使用し** て、コマンドの進行状況を表示します。</span><span class="sxs-lookup"><span data-stu-id="09c91-298">**Import-PSSession** uses the Write-Progress cmdlet to display the progress of the command.</span></span> <span data-ttu-id="09c91-299">コマンドが実行中の場合、進行状況バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09c91-299">You might see the progress bar while the command is running.</span></span>
* <span data-ttu-id="09c91-300">インポートするコマンドを見つけるには、Invoke-Command コマンドレット **を使用し** て、pssession で Get-Command コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="09c91-300">To find the commands to import, **Import-PSSession** uses the Invoke-Command cmdlet to run a Get-Command command in the PSSession.</span></span> <span data-ttu-id="09c91-301">コマンドの書式設定データを取得するには、Get-FormatData コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="09c91-301">To get formatting data for the commands, it uses the Get-FormatData cmdlet.</span></span> <span data-ttu-id="09c91-302">これらのコマンドレットのエラーメッセージは、 **インポート-PSSession** コマンドを実行すると表示できます。</span><span class="sxs-lookup"><span data-stu-id="09c91-302">You might see error messages from these cmdlets when you run an **Import-PSSession** command.</span></span> <span data-ttu-id="09c91-303">また、 **インポート pssession** では、コマンドレットの get Command、Get Formatdata、Select-Object、および Get-Help を含まない pssession からコマンドをインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="09c91-303">Also, **Import-PSSession** cannot import commands from a PSSession that does not include the Get-Command, Get-FormatData, Select-Object, and Get-Help cmdlets.</span></span>
* <span data-ttu-id="09c91-304">インポートされたコマンドには、ユーザー インターフェイスを備えたプログラム (たとえば、メモ帳) を起動できないなど、他のリモート コマンドと同じ制限があります。</span><span class="sxs-lookup"><span data-stu-id="09c91-304">Imported commands have the same limitations as other remote commands, including the inability to start a program with a user interface, such as Notepad.</span></span>
* <span data-ttu-id="09c91-305">PowerShell プロファイルは PSSessions では実行されないため、プロファイルによってセッションに追加されるコマンドは、 **インポート-PSSession** では使用できません。</span><span class="sxs-lookup"><span data-stu-id="09c91-305">Because PowerShell profiles are not run in PSSessions, the commands that a profile adds to a session are not available to **Import-PSSession** .</span></span> <span data-ttu-id="09c91-306">プロファイルからコマンドをインポートするには、コマンドをインポートする前に、Invoke-Command コマンドを使用して、PSSession でプロファイルを手動で実行します。</span><span class="sxs-lookup"><span data-stu-id="09c91-306">To import commands from a profile, use an Invoke-Command command to run the profile in the PSSession manually before importing commands.</span></span>
* <span data-ttu-id="09c91-307">**Import-PSSession** によって作成された一時的なモジュールには、そのコマンドで書式データがインポートされない場合でも、書式ファイルが含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="09c91-307">The temporary module that **Import-PSSession** creates might include a formatting file, even if the command does not import formatting data.</span></span> <span data-ttu-id="09c91-308">コマンドで書式データがインポートされない場合、作成される書式ファイルに書式データは含まれません。</span><span class="sxs-lookup"><span data-stu-id="09c91-308">If the command does not import formatting data, any formatting files that are created will not contain formatting data.</span></span>
* <span data-ttu-id="09c91-309">**Import-PSSession** を使用する場合は、現在のセッションの実行ポリシーを Restricted または AllSigned に設定することはできません。これは、 **Import-PSSession** によって作成される一時的なモジュールに含まれる未署名のスクリプト ファイルがこれらのポリシーによって禁止されているためです。</span><span class="sxs-lookup"><span data-stu-id="09c91-309">To use **Import-PSSession** , the execution policy in the current session cannot be Restricted or AllSigned, because the temporary module that **Import-PSSession** creates contains unsigned script files that are prohibited by these policies.</span></span> <span data-ttu-id="09c91-310">ローカルコンピューターの実行ポリシーを変更せずに **インポート PSSession** を使用するには、Set-ExecutionPolicy の *Scope* パラメーターを使用して、1つのプロセスに対して制限の少ない実行ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="09c91-310">To use **Import-PSSession** without changing the execution policy for the local computer, use the *Scope* parameter of Set-ExecutionPolicy to set a less restrictive execution policy for a single process.</span></span>
* <span data-ttu-id="09c91-311">Windows PowerShell 2.0 では、別のセッションからインポートしたコマンドのヘルプ トピックに、 *Prefix* パラメーターを使用して割り当てたプレフィックスが含まれません。</span><span class="sxs-lookup"><span data-stu-id="09c91-311">In Windows PowerShell 2.0, help topics for commands that are imported from another session do not include the prefix that you assign by using the *Prefix* parameter.</span></span> <span data-ttu-id="09c91-312">Windows PowerShell 2.0 でインポートしたコマンドのヘルプを取得するには、元の (プレフィックスなしの) コマンド名を使用します。</span><span class="sxs-lookup"><span data-stu-id="09c91-312">To get help for an imported command in Windows PowerShell 2.0, use the original (non-prefixed) command name.</span></span>

## <span data-ttu-id="09c91-313">関連リンク</span><span class="sxs-lookup"><span data-stu-id="09c91-313">RELATED LINKS</span></span>

[<span data-ttu-id="09c91-314">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="09c91-314">Export-PSSession</span></span>](Export-PSSession.md)
