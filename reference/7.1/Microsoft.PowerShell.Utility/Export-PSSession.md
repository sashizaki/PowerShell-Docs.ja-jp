---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-PSSession
ms.openlocfilehash: 2fda80c934db3e868f0e49e131e6721c7b899f7c
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "93218008"
---
# <span data-ttu-id="d1701-103">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="d1701-103">Export-PSSession</span></span>

## <span data-ttu-id="d1701-104">概要</span><span class="sxs-lookup"><span data-stu-id="d1701-104">SYNOPSIS</span></span>

<span data-ttu-id="d1701-105">別のセッションからコマンドをエクスポートし、PowerShell モジュールに保存します。</span><span class="sxs-lookup"><span data-stu-id="d1701-105">Exports commands from another session and saves them in a PowerShell module.</span></span>

## <span data-ttu-id="d1701-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d1701-106">SYNTAX</span></span>

### <span data-ttu-id="d1701-107">All</span><span class="sxs-lookup"><span data-stu-id="d1701-107">All</span></span>

```
Export-PSSession [-OutputModule] <String> [-Force] [-Encoding <Encoding>]
 [[-CommandName] <String[]>] [-AllowClobber] [-ArgumentList <Object[]>]
 [-CommandType <CommandTypes>] [-Module <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-FormatTypeName] <String[]>] [-Certificate <X509Certificate2>] [-Session] <PSSession>
 [<CommonParameters>]
```

## <span data-ttu-id="d1701-108">Description</span><span class="sxs-lookup"><span data-stu-id="d1701-108">DESCRIPTION</span></span>

<span data-ttu-id="d1701-109">コマンド `Export-PSSession` レットは、ローカルコンピューターまたはリモートコンピューター上の別の powershell セッション (PSSession) からコマンドレット、関数、エイリアス、およびその他のコマンドの種類を取得し、powershell モジュールに保存します。</span><span class="sxs-lookup"><span data-stu-id="d1701-109">The `Export-PSSession` cmdlet gets cmdlets, functions, aliases, and other command types from another PowerShell session (PSSession) on a local or remote computer and saves them in a PowerShell module.</span></span> <span data-ttu-id="d1701-110">モジュールのコマンドを現在のセッションに追加するには、コマンドレットを使用し `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-110">To add the commands from the module to the current session, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="d1701-111">`Import-PSSession`別の PSSession から現在のセッションにコマンドをインポートするとは異なり、は `Export-PSSession` モジュールにコマンドを保存します。</span><span class="sxs-lookup"><span data-stu-id="d1701-111">Unlike `Import-PSSession`, which imports commands from another PSSession into the current session, `Export-PSSession` saves the commands in a module.</span></span> <span data-ttu-id="d1701-112">コマンドは、現在のセッションにはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="d1701-112">The commands are not imported into the current session.</span></span>

<span data-ttu-id="d1701-113">コマンドをエクスポートするには、コマンドレットを使用して、 `New-PSSession` エクスポートするコマンドを含む PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1701-113">To export commands, use the `New-PSSession` cmdlet to create a PSSession that has the commands that you want to export.</span></span> <span data-ttu-id="d1701-114">次に、 `Export-PSSession` コマンドレットを使用してコマンドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d1701-114">Then use the `Export-PSSession` cmdlet to export the commands.</span></span>

<span data-ttu-id="d1701-115">コマンド名の競合を防ぐため、の既定で `Export-PSSession` は、現在のセッションに存在するコマンドを除き、すべてのコマンドがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="d1701-115">To prevent command name conflicts, the default for `Export-PSSession` is to export all commands, except for commands that exist in the current session.</span></span> <span data-ttu-id="d1701-116">**CommandName** パラメーターを使用して、エクスポートするコマンドを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d1701-116">You can use the **CommandName** parameter to specify the commands to export.</span></span>

<span data-ttu-id="d1701-117">`Export-PSSession`コマンドレットでは、PowerShell の暗黙的なリモート処理機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1701-117">The `Export-PSSession` cmdlet uses the implicit remoting feature of PowerShell.</span></span> <span data-ttu-id="d1701-118">現在のセッションにコマンドをインポートすると、元のセッションまたは元のコンピューターの同様のセッションで、コマンドが暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="d1701-118">When you import commands into the current session, they run implicitly in the original session or in a similar session on the originating computer.</span></span>

## <span data-ttu-id="d1701-119">例</span><span class="sxs-lookup"><span data-stu-id="d1701-119">EXAMPLES</span></span>

### <span data-ttu-id="d1701-120">例 1: PSSession からコマンドをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d1701-120">Example 1: Export commands from a PSSession</span></span>

<span data-ttu-id="d1701-121">この例では、ローカルコンピューターから Server01 コンピューターに新しい PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1701-121">This example creates a new PSSession from the local computer to the Server01 computer.</span></span> <span data-ttu-id="d1701-122">現在のセッションに存在するコマンドを除くすべてのコマンドは、ローカルコンピューター上の Server01 という名前のモジュールにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="d1701-122">All of the commands, except those that exist in the current session, are exported to the module named Server01 on the local computer.</span></span> <span data-ttu-id="d1701-123">エクスポートには、コマンドの書式設定データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1701-123">The export includes the formatting data for the commands.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01
Export-PSSession -Session $S -OutputModule Server01
```

<span data-ttu-id="d1701-124">この `New-PSSession` コマンドは、Server01 コンピューター上に PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1701-124">The `New-PSSession` command creates a PSSession on the Server01 computer.</span></span> <span data-ttu-id="d1701-125">PSSession は変数に格納され `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-125">The PSSession is stored in the `$S` variable.</span></span> <span data-ttu-id="d1701-126">この `Export-PSSession` コマンドは、 `$S` 変数のコマンドをエクスポートし、Server01 モジュールにデータを書式設定します。</span><span class="sxs-lookup"><span data-stu-id="d1701-126">The `Export-PSSession` command exports the `$S` variable's commands and formatting data into the Server01 module.</span></span>

### <span data-ttu-id="d1701-127">例 2: Get コマンドと Set コマンドをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d1701-127">Example 2: Export the Get and Set commands</span></span>

<span data-ttu-id="d1701-128">この例では、 `Get` サーバーからすべてのコマンドとコマンドをエクスポートし `Set` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-128">This example exports all of the `Get` and `Set` commands from a server.</span></span>

```powershell
$S = New-PSSession -ConnectionUri https://exchange.microsoft.com/mailbox -Credential exchangeadmin01@hotmail.com -Authentication Negotiate
Export-PSSession -Session $S -Module exch* -CommandName Get-*, Set-* -FormatTypeName * -OutputModule $PSHOME\Modules\Exchange -Encoding ASCII
```

<span data-ttu-id="d1701-129">これらのコマンドは `Get` 、 `Set` リモートコンピューター上の Microsoft exchange Server スナップインからローカルコンピューター上のディレクトリの Exchange モジュールに、コマンドとコマンドをエクスポートし `$PSHOME\Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-129">These commands export the `Get` and `Set` commands from a Microsoft Exchange Server snap-in on a remote computer to an Exchange module in the `$PSHOME\Modules` directory on the local computer.</span></span>
<span data-ttu-id="d1701-130">ディレクトリにモジュールを配置 `$PSHOME\Modules` すると、コンピューターのすべてのユーザーがそのモジュールにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="d1701-130">Placing the module in the `$PSHOME\Modules` directory makes it accessible to all users of the computer.</span></span>

### <span data-ttu-id="d1701-131">例 3: リモートコンピューターからコマンドをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d1701-131">Example 3: Export commands from a remote computer</span></span>

<span data-ttu-id="d1701-132">この例では、リモートコンピューター上の PSSession からコマンドレットをエクスポートし、ローカルコンピューター上のモジュールに保存します。</span><span class="sxs-lookup"><span data-stu-id="d1701-132">This example exports cmdlets from a PSSession on a remote computer and saves them in a module on the local computer.</span></span> <span data-ttu-id="d1701-133">モジュールのコマンドレットが現在のセッションに追加され、使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d1701-133">The cmdlets from the module are added to the current session so that they can be used.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01 -Credential Server01\User01
Export-PSSession -Session $S -OutputModule TestCmdlets -Type Cmdlet -CommandName *test* -FormatTypeName *
Remove-PSSession $S
Import-Module TestCmdlets
Get-Help Test*
Test-Files
```

<span data-ttu-id="d1701-134">`New-PSSession`このコマンドは、Server01 コンピューター上に PSSession を作成し、変数に保存し `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-134">The `New-PSSession` command creates a PSSession on the Server01 computer and saves it in the `$S` variable.</span></span> <span data-ttu-id="d1701-135">コマンドは、 `Export-PSSession` の PSSession から `$S` ローカルコンピューター上の testcmdlets モジュールへのテストで名前が始まるコマンドレットをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d1701-135">The `Export-PSSession` command exports the cmdlets whose names begin with Test from the PSSession in `$S` to the TestCmdlets module on the local computer.</span></span>

<span data-ttu-id="d1701-136">`Remove-PSSession`コマンドレットでは、の PSSession を `$S` 現在のセッションから削除します。</span><span class="sxs-lookup"><span data-stu-id="d1701-136">The `Remove-PSSession` cmdlet deletes the PSSession in `$S` from the current session.</span></span> <span data-ttu-id="d1701-137">このコマンドは、セッションからインポートされたコマンドを使用するために PSSession をアクティブにする必要がないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="d1701-137">This command shows that the PSSession need not be active to use the commands that were imported from the session.</span></span> <span data-ttu-id="d1701-138">コマンドレットでは、 `Import-Module` testcmdlets モジュール内のコマンドレットを現在のセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="d1701-138">The `Import-Module` cmdlet adds the cmdlets in the TestCmdlets module to the current session.</span></span> <span data-ttu-id="d1701-139">コマンドは、任意のセッションでいつでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="d1701-139">The command can be run in any session at any time.</span></span>

<span data-ttu-id="d1701-140">`Get-Help`コマンドレットは、名前が Test で始まるコマンドレットのヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="d1701-140">The `Get-Help` cmdlet gets help for cmdlets whose names begin with Test.</span></span> <span data-ttu-id="d1701-141">モジュール内のコマンドを現在のセッションに追加した後は、コマンドレットとコマンドレットを使用して、インポートした `Get-Help` `Get-Command` コマンドについて学習できます。</span><span class="sxs-lookup"><span data-stu-id="d1701-141">After the commands in a module are added to the current session, you can use the `Get-Help` and `Get-Command` cmdlets to learn about the imported commands.</span></span> <span data-ttu-id="d1701-142">`Test-Files`コマンドレットが Server01 コンピューターからエクスポートされ、セッションに追加されました。</span><span class="sxs-lookup"><span data-stu-id="d1701-142">The `Test-Files` cmdlet was exported from the Server01 computer and added to the session.</span></span> <span data-ttu-id="d1701-143">`Test-Files`コマンドレットは、コマンドがインポートされたコンピューター上のリモートセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="d1701-143">The `Test-Files` cmdlet runs in a remote session on the computer from which the command was imported.</span></span> <span data-ttu-id="d1701-144">PowerShell は、TestCmdlets モジュールに格納されている情報からセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1701-144">PowerShell creates a session from information that is stored in the TestCmdlets module.</span></span>

### <span data-ttu-id="d1701-145">例 4: 現在のセッションでコマンドを Export および上書きする</span><span class="sxs-lookup"><span data-stu-id="d1701-145">Example 4: Export and clobber commands in the current session</span></span>

<span data-ttu-id="d1701-146">この例では、変数に格納されているコマンドを現在のセッションにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d1701-146">This example exports commands that are stored in a variable into the current session.</span></span>

```powershell
Export-PSSession -Session $S -AllowClobber -OutputModule AllCommands
```

<span data-ttu-id="d1701-147">この `Export-PSSession` コマンドは、変数内の PSSession から現在のセッションにすべてのコマンドおよびすべての書式設定データをエクスポートし `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-147">This `Export-PSSession` command exports all commands and all formatting data from the PSSession in the `$S` variable into the current session.</span></span> <span data-ttu-id="d1701-148">**AllowClobber** パラメーターには、現在のセッションのコマンドと同じ名前のコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1701-148">The **AllowClobber** parameter includes commands with the same names as commands in the current session.</span></span>

### <span data-ttu-id="d1701-149">例 5: 閉じた PSSession からコマンドをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d1701-149">Example 5: Export commands from a closed PSSession</span></span>

<span data-ttu-id="d1701-150">この例では、エクスポートされたコマンドを作成した PSSession が閉じているときに、特別なオプションを使用してエクスポートされたコマンドを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d1701-150">This example shows how to run the exported commands with special options when the PSSession that created the exported commands is closed.</span></span>

<span data-ttu-id="d1701-151">モジュールをインポートするときに元のリモートセッションが閉じている場合、モジュールは、元のコンピューターに接続している開いているリモートセッションを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1701-151">If the original remote session is closed when a module is imported, the module will use any open remote session that connects to the originating computer.</span></span> <span data-ttu-id="d1701-152">発信元のコンピューターに現在のセッションがない場合は、モジュールによってセッションが再確立されます。</span><span class="sxs-lookup"><span data-stu-id="d1701-152">If there is no current session to the originating computer, the module will reestablish a session.</span></span>

<span data-ttu-id="d1701-153">リモートセッションで特別なオプションを指定してエクスポートされたコマンドを実行するには、モジュールをインポートする前に、これらのオプションを使用してリモートセッションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1701-153">To run exported commands with special options in a remote session, you must create a remote session with those options before you import the module.</span></span> <span data-ttu-id="d1701-154">`New-PSSession` **Sessionoption** パラメーターを指定してコマンドレットを使用する</span><span class="sxs-lookup"><span data-stu-id="d1701-154">Use the `New-PSSession` cmdlet with the **SessionOption** parameter</span></span>

```powershell
$Options = New-PSSessionOption -NoMachineProfile
$S = New-PSSession -ComputerName Server01 -SessionOption $Options
Export-PSSession -Session $S -OutputModule Server01
Remove-PSSession $S
New-PSSession -ComputerName Server01 -SessionOption $Options
Import-Module Server01
```

<span data-ttu-id="d1701-155">コマンドレットでは、 `New-PSSessionOption` **Pssessionoption** オブジェクトを作成し、そのオブジェクトを変数に保存し `$Options` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-155">The `New-PSSessionOption` cmdlet creates a **PSSessionOption** object, and it saves the object in the `$Options` variable.</span></span> <span data-ttu-id="d1701-156">この `New-PSSession` コマンドは、Server01 コンピューター上に PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1701-156">The `New-PSSession` command creates a PSSession on the Server01 computer.</span></span>
<span data-ttu-id="d1701-157">**Sessionoption** パラメーターは、に格納されているオブジェクトを使用し `$Options` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-157">The **SessionOption** parameter uses the object stored in `$Options`.</span></span> <span data-ttu-id="d1701-158">セッションは変数に格納され `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-158">The session is stored in the `$S` variable.</span></span>

<span data-ttu-id="d1701-159">コマンド `Export-PSSession` レットは、の PSSession から `$S` Server01 モジュールにコマンドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d1701-159">The `Export-PSSession` cmdlet exports commands from the PSSession in `$S` to the Server01 module.</span></span>
<span data-ttu-id="d1701-160">この `Remove-PSSession` コマンドレットは、変数内の PSSession を削除し `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-160">The `Remove-PSSession` cmdlet deletes the PSSession in the `$S` variable.</span></span>

<span data-ttu-id="d1701-161">コマンドレットでは、 `New-PSSession` Server01 コンピューターに接続する新しい PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1701-161">The `New-PSSession` cmdlet creates a new PSSession that connects to the Server01 computer.</span></span> <span data-ttu-id="d1701-162">**Sessionoption** パラメーターは、に格納されているオブジェクトを使用し `$Options` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-162">The **SessionOption** parameter uses the object stored in `$Options`.</span></span> <span data-ttu-id="d1701-163">`Import-Module`コマンドレットは、Server01 モジュールからコマンドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d1701-163">The `Import-Module` cmdlet imports the commands from the Server01 module.</span></span> <span data-ttu-id="d1701-164">モジュール内のコマンドは、Server01 コンピューター上の PSSession で実行されます。</span><span class="sxs-lookup"><span data-stu-id="d1701-164">The commands in the module are run in the PSSession on the Server01 computer.</span></span>

## <span data-ttu-id="d1701-165">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d1701-165">PARAMETERS</span></span>

### <span data-ttu-id="d1701-166">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="d1701-166">-AllowClobber</span></span>

<span data-ttu-id="d1701-167">現在のセッションのコマンドと同じ名前でも、指定されたコマンドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d1701-167">Exports the specified commands, even if they have the same names as commands in the current session.</span></span>

<span data-ttu-id="d1701-168">現在のセッションのコマンドと同じ名前のコマンドをエクスポートすると、エクスポートされたコマンドは元のコマンドを非表示にしたり置き換えたりします。</span><span class="sxs-lookup"><span data-stu-id="d1701-168">If you export a command with the same name as a command in the current session, the exported command hides or replaces the original commands.</span></span> <span data-ttu-id="d1701-169">詳細については、「[about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md)」(コマンドの優先順位について) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1701-169">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span></span>

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

### <span data-ttu-id="d1701-170">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="d1701-170">-ArgumentList</span></span>

<span data-ttu-id="d1701-171">指定された引数 (パラメーター値) を使用して生成されたコマンドのバリアントをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d1701-171">Exports the variant of the command that results from using the specified arguments (parameter values).</span></span>

<span data-ttu-id="d1701-172">たとえば、証明書内のコマンドのバリアントをエクスポートするには `Get-Item` (Cert:)の PSSession のドライブに `$S` 、「」と入力 `Export-PSSession -Session $S -Command Get-Item -ArgumentList cert:` します。</span><span class="sxs-lookup"><span data-stu-id="d1701-172">For example, to export the variant of the `Get-Item` command in the certificate (Cert:) drive in the PSSession in `$S`, type `Export-PSSession -Session $S -Command Get-Item -ArgumentList cert:`.</span></span>

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

### <span data-ttu-id="d1701-173">-証明書</span><span class="sxs-lookup"><span data-stu-id="d1701-173">-Certificate</span></span>

<span data-ttu-id="d1701-174">を作成するモジュールで、フォーマットファイル (\* .Format.ps1xml) またはスクリプトモジュールファイル (hbase-runner.psm1) の署名に使用されるクライアント証明書を指定し `Export-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-174">Specifies the client certificate that is used to sign the format files (\*.Format.ps1xml) or script module files (.psm1) in the module that `Export-PSSession` creates.</span></span> <span data-ttu-id="d1701-175">証明書が格納されている変数を入力するか、証明書を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="d1701-175">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="d1701-176">証明書を検索するには、コマンドレットを使用する `Get-PfxCertificate` か、 `Get-ChildItem` 証明書 (Cert:) のコマンドレットを使用します。駆動.</span><span class="sxs-lookup"><span data-stu-id="d1701-176">To find a certificate, use the `Get-PfxCertificate` cmdlet or use the `Get-ChildItem` cmdlet in the Certificate (Cert:) drive.</span></span> <span data-ttu-id="d1701-177">証明書が無効な場合、または証明書に十分な権限がない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="d1701-177">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="d1701-178">-CommandName</span><span class="sxs-lookup"><span data-stu-id="d1701-178">-CommandName</span></span>

<span data-ttu-id="d1701-179">指定した名前または名前パターンのコマンドのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d1701-179">Exports only the commands with the specified names or name patterns.</span></span> <span data-ttu-id="d1701-180">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1701-180">Wildcards are permitted.</span></span> <span data-ttu-id="d1701-181">**CommandName** またはそのエイリアスである **Name** を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1701-181">Use **CommandName** or its alias, **Name**.</span></span>

<span data-ttu-id="d1701-182">既定では、は、 `Export-PSSession` 現在のセッションのコマンドと同じ名前を持つコマンドを除き、PSSession からすべてのコマンドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d1701-182">By default, `Export-PSSession` exports all commands from the PSSession except for commands that have the same names as commands in the current session.</span></span> <span data-ttu-id="d1701-183">これにより、現在のセッションのコマンドによってコマンドが非表示になったり置き換えられたりするのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="d1701-183">This prevents commands from being hidden or replaced by commands in the current session.</span></span> <span data-ttu-id="d1701-184">他のコマンドを表示または置換するコマンドも含めて、すべてのコマンドをエクスポートするには、 **AllowClobber** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1701-184">To export all commands, even those that hide or replace other commands, use the **AllowClobber** parameter.</span></span>

<span data-ttu-id="d1701-185">**CommandName** パラメーターを使用する場合、 **formattypename** パラメーターを使用しない限り、コマンドの書式設定ファイルはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="d1701-185">If you use the **CommandName** parameter, the formatting files for the commands are not exported unless you use the **FormatTypeName** parameter.</span></span> <span data-ttu-id="d1701-186">同様に、 **Formattypename** パラメーターを使用する場合、 **CommandName** パラメーターを使用しない限り、コマンドはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="d1701-186">Similarly, if you use the **FormatTypeName** parameter, no commands are exported unless you use the **CommandName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d1701-187">-CommandType</span><span class="sxs-lookup"><span data-stu-id="d1701-187">-CommandType</span></span>

<span data-ttu-id="d1701-188">指定された型のコマンド オブジェクトのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d1701-188">Exports only the specified types of command objects.</span></span> <span data-ttu-id="d1701-189">**CommandType** またはそのエイリアスの **Type** を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1701-189">Use **CommandType** or its alias, **Type**.</span></span>

<span data-ttu-id="d1701-190">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d1701-190">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="d1701-191">エイリアス.</span><span class="sxs-lookup"><span data-stu-id="d1701-191">Alias.</span></span> <span data-ttu-id="d1701-192">現在のセッションのすべての PowerShell エイリアス。</span><span class="sxs-lookup"><span data-stu-id="d1701-192">All PowerShell aliases in the current session.</span></span>
- <span data-ttu-id="d1701-193">すべて。</span><span class="sxs-lookup"><span data-stu-id="d1701-193">All.</span></span> <span data-ttu-id="d1701-194">すべてのコマンドの型。</span><span class="sxs-lookup"><span data-stu-id="d1701-194">All command types.</span></span> <span data-ttu-id="d1701-195">これは、と同じです `Get-Command -Name *` 。</span><span class="sxs-lookup"><span data-stu-id="d1701-195">It is the equivalent of `Get-Command -Name *`.</span></span>
- <span data-ttu-id="d1701-196">アプリケーション をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1701-196">Application.</span></span> <span data-ttu-id="d1701-197">Path 環境変数 () に一覧表示されているパス内の PowerShell ファイル以外のすべてのファイル ( `$env:path` .txt、.exe、.dll ファイルなど)。</span><span class="sxs-lookup"><span data-stu-id="d1701-197">All files other than PowerShell files in paths listed in the Path environment variable (`$env:path`), including .txt, .exe, and .dll files.</span></span>
- <span data-ttu-id="d1701-198">コマンドレット.</span><span class="sxs-lookup"><span data-stu-id="d1701-198">Cmdlet.</span></span> <span data-ttu-id="d1701-199">現在のセッションのコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="d1701-199">The cmdlets in the current session.</span></span> <span data-ttu-id="d1701-200">コマンドレットが既定値です。</span><span class="sxs-lookup"><span data-stu-id="d1701-200">Cmdlet is the default.</span></span>
- <span data-ttu-id="d1701-201">構成。</span><span class="sxs-lookup"><span data-stu-id="d1701-201">Configuration.</span></span> <span data-ttu-id="d1701-202">PowerShell 構成。</span><span class="sxs-lookup"><span data-stu-id="d1701-202">A PowerShell configuration.</span></span> <span data-ttu-id="d1701-203">詳細については、「 [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1701-203">For more information, see [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span></span>
- <span data-ttu-id="d1701-204">ExternalScript。</span><span class="sxs-lookup"><span data-stu-id="d1701-204">ExternalScript.</span></span> <span data-ttu-id="d1701-205">Path 環境変数 () に示されているパス内のすべての ps1 ファイル。 `$env:path`</span><span class="sxs-lookup"><span data-stu-id="d1701-205">All .ps1 files in the paths listed in the Path environment variable (`$env:path`).</span></span>
- <span data-ttu-id="d1701-206">フィルターと関数。</span><span class="sxs-lookup"><span data-stu-id="d1701-206">Filter and Function.</span></span> <span data-ttu-id="d1701-207">すべての PowerShell 関数。</span><span class="sxs-lookup"><span data-stu-id="d1701-207">All PowerShell functions.</span></span>
- <span data-ttu-id="d1701-208">スクリプティング。</span><span class="sxs-lookup"><span data-stu-id="d1701-208">Script.</span></span> <span data-ttu-id="d1701-209">現在のセッションのスクリプト ブロック。</span><span class="sxs-lookup"><span data-stu-id="d1701-209">Script blocks in the current session.</span></span>
- <span data-ttu-id="d1701-210">稟議.</span><span class="sxs-lookup"><span data-stu-id="d1701-210">Workflow.</span></span> <span data-ttu-id="d1701-211">PowerShell ワークフロー。</span><span class="sxs-lookup"><span data-stu-id="d1701-211">A PowerShell workflow.</span></span> <span data-ttu-id="d1701-212">詳細については、「 [about_Workflows](/powershell/module/psworkflow/about/about_workflows?view=powershell-5.1)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1701-212">For more information, see [about_Workflows](/powershell/module/psworkflow/about/about_workflows?view=powershell-5.1).</span></span>

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, All, Application, Cmdlet, Configuration, ExternalScript, Filter, Function, Script, Workflow

Required: False
Position: Named
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d1701-213">-Encoding</span><span class="sxs-lookup"><span data-stu-id="d1701-213">-Encoding</span></span>

<span data-ttu-id="d1701-214">ターゲット ファイルのエンコードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1701-214">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="d1701-215">既定値は `utf8NoBOM` です。</span><span class="sxs-lookup"><span data-stu-id="d1701-215">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="d1701-216">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d1701-216">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="d1701-217">`ascii`: ASCII (7 ビット) 文字セットのエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1701-217">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="d1701-218">`bigendianunicode`: ビッグエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d1701-218">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="d1701-219">`bigendianutf32`: ビッグエンディアンのバイト順を使用して、32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d1701-219">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="d1701-220">`oem`: MS-DOS およびコンソールプログラムの既定のエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1701-220">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="d1701-221">`unicode`: リトルエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d1701-221">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="d1701-222">`utf7`: UTF-7 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d1701-222">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="d1701-223">`utf8`: UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d1701-223">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="d1701-224">`utf8BOM`: バイト順マーク (BOM) を使用して UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d1701-224">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="d1701-225">`utf8NoBOM`: バイトオーダーマーク (BOM) を使用せずに UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d1701-225">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="d1701-226">`utf32`:32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d1701-226">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="d1701-227">PowerShell 6.2 以降では、 **Encoding** パラメーターを使用して、登録されているコードページの数値 id (など) `-Encoding 1251` や、登録されているコードページの文字列名 (など) を使用することもでき `-Encoding "windows-1251"` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-227">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="d1701-228">詳細については、 [コードページ](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)の .net ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1701-228">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d1701-229">-Force</span><span class="sxs-lookup"><span data-stu-id="d1701-229">-Force</span></span>

<span data-ttu-id="d1701-230">ファイルが読み取り専用属性を持つ場合でも、1 つ以上の既存の出力ファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="d1701-230">Overwrites one or more existing output files, even if the file has the read-only attribute.</span></span>

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

### <span data-ttu-id="d1701-231">-FormatTypeName</span><span class="sxs-lookup"><span data-stu-id="d1701-231">-FormatTypeName</span></span>

<span data-ttu-id="d1701-232">指定された Microsoft .NET Framework 型の書式設定命令をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d1701-232">Exports formatting instructions only for the specified Microsoft .NET Framework types.</span></span> <span data-ttu-id="d1701-233">型名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d1701-233">Enter the type names.</span></span> <span data-ttu-id="d1701-234">既定では、は、 `Export-PSSession` .NET Framework の名前空間に含まれてい **System.Management.Automation** ないすべての型の書式設定命令をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d1701-234">By default, `Export-PSSession` exports formatting instructions for all .NET Framework types that are not in the **System.Management.Automation** namespace.</span></span>

<span data-ttu-id="d1701-235">このパラメーターの値は、コマンドがインポートされるセッション内のコマンドによって返される型の名前である必要があり `Get-FormatData` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-235">The value of this parameter must be the name of a type that is returned by a `Get-FormatData` command in the session from which the commands are being imported.</span></span> <span data-ttu-id="d1701-236">リモートセッションのすべての書式設定データを取得するには、「」と入力 `*` します。</span><span class="sxs-lookup"><span data-stu-id="d1701-236">To get all of the formatting data in the remote session, type `*`.</span></span>

<span data-ttu-id="d1701-237">**Formattypename** パラメーターを使用する場合、 **CommandName** パラメーターを使用しない限り、コマンドはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="d1701-237">If you use the **FormatTypeName** parameter, no commands are exported unless you use the **CommandName** parameter.</span></span>

<span data-ttu-id="d1701-238">**CommandName** パラメーターを使用する場合、 **formattypename** パラメーターを使用しない限り、コマンドの書式設定ファイルはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="d1701-238">If you use the **CommandName** parameter, the formatting files for the commands are not exported unless you use the **FormatTypeName** parameter.</span></span>

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

### <span data-ttu-id="d1701-239">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="d1701-239">-FullyQualifiedModule</span></span>

<span data-ttu-id="d1701-240">**Modul特定** のオブジェクトの形式で指定された名前を持つモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="d1701-240">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span>
<span data-ttu-id="d1701-241">「 [Modulの認識コンストラクター (Hashtable)](https://msdn.microsoft.com/library/jj136290)」の「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1701-241">See the Remarks section of [ModuleSpecification Constructor (Hashtable)](https://msdn.microsoft.com/library/jj136290).</span></span>

<span data-ttu-id="d1701-242">たとえば、 **FullyQualifiedModule** パラメーターは、次のいずれかの形式で指定されたモジュール名を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="d1701-242">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in either of these formats:</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"}`

`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="d1701-243">**ModuleName** と **ModuleVersion** は必須ですが、 **Guid** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d1701-243">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span> <span data-ttu-id="d1701-244">**モジュール** パラメーターと同じコマンドで **FullyQualifiedModule** パラメーターを指定することはできません。2つのパラメーターは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="d1701-244">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter; the two parameters are mutually exclusive.</span></span>

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

### <span data-ttu-id="d1701-245">-モジュール</span><span class="sxs-lookup"><span data-stu-id="d1701-245">-Module</span></span>

<span data-ttu-id="d1701-246">指定した PowerShell スナップインおよびモジュールのコマンドのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d1701-246">Exports only the commands in the specified PowerShell snap-ins and modules.</span></span> <span data-ttu-id="d1701-247">スナップインとモジュールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d1701-247">Enter the snap-in and module names.</span></span> <span data-ttu-id="d1701-248">ワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="d1701-248">Wildcards are not permitted.</span></span>

<span data-ttu-id="d1701-249">詳細については、「」および about_PSSnapins を参照してください `Import-Module` 。 [about_PSSnapins](/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1)</span><span class="sxs-lookup"><span data-stu-id="d1701-249">For more information, see `Import-Module` and [about_PSSnapins](/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d1701-250">-OutputModule</span><span class="sxs-lookup"><span data-stu-id="d1701-250">-OutputModule</span></span>

<span data-ttu-id="d1701-251">によって作成されたモジュールのパスと名前 (省略可能) を指定し `Export-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-251">Specifies an optional path and name for the module created by `Export-PSSession`.</span></span> <span data-ttu-id="d1701-252">既定のパスは、`$home\Documents\WindowsPowerShell\Modules` です。</span><span class="sxs-lookup"><span data-stu-id="d1701-252">The default path is `$home\Documents\WindowsPowerShell\Modules`.</span></span> <span data-ttu-id="d1701-253">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="d1701-253">This parameter is required.</span></span>

<span data-ttu-id="d1701-254">モジュールサブディレクトリまたはが作成したファイルが `Export-PSSession` 既に存在する場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="d1701-254">If the module subdirectory or any of the files that `Export-PSSession` creates already exist, the command fails.</span></span> <span data-ttu-id="d1701-255">既存のファイルを上書きするには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1701-255">To overwrite existing files, use the **Force** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, ModuleName

Required: True
Position: 1
Default value: $home\Documents\WindowsPowerShell\Modules
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d1701-256">-セッション</span><span class="sxs-lookup"><span data-stu-id="d1701-256">-Session</span></span>

<span data-ttu-id="d1701-257">コマンドのエクスポート元の PSSession を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1701-257">Specifies the PSSession from which the commands are exported.</span></span> <span data-ttu-id="d1701-258">セッションオブジェクトを含む変数、またはコマンドなどのセッションオブジェクトを取得するコマンドを入力し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-258">Enter a variable that contains a session object or a command that gets a session object, such as a `Get-PSSession` command.</span></span> <span data-ttu-id="d1701-259">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="d1701-259">This parameter is required.</span></span>

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

### <span data-ttu-id="d1701-260">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d1701-260">CommonParameters</span></span>

<span data-ttu-id="d1701-261">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d1701-261">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d1701-262">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1701-262">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d1701-263">入力</span><span class="sxs-lookup"><span data-stu-id="d1701-263">INPUTS</span></span>

### <span data-ttu-id="d1701-264">なし</span><span class="sxs-lookup"><span data-stu-id="d1701-264">None</span></span>

<span data-ttu-id="d1701-265">パイプを使用してオブジェクトをにパイプすることはできません `Export-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="d1701-265">You cannot pipe objects to `Export-PSSession`.</span></span>

## <span data-ttu-id="d1701-266">出力</span><span class="sxs-lookup"><span data-stu-id="d1701-266">OUTPUTS</span></span>

### <span data-ttu-id="d1701-267">システム. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="d1701-267">System.IO.FileInfo</span></span>

<span data-ttu-id="d1701-268">`Export-PSSession` 作成したモジュールを構成するファイルの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="d1701-268">`Export-PSSession` returns a list of files that comprise the module that it created.</span></span>

## <span data-ttu-id="d1701-269">注</span><span class="sxs-lookup"><span data-stu-id="d1701-269">NOTES</span></span>

<span data-ttu-id="d1701-270">`Export-PSSession` は、PowerShell リモート処理インフラストラクチャに依存しています。</span><span class="sxs-lookup"><span data-stu-id="d1701-270">`Export-PSSession` relies on the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="d1701-271">このコマンドレットを使用するには、リモート用にコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1701-271">To use this cmdlet, the computer must be configured for remoting.</span></span> <span data-ttu-id="d1701-272">詳細については、「[about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1701-272">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="d1701-273">を使用して `Export-PSSession` PowerShell プロバイダーをエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d1701-273">You cannot use `Export-PSSession` to export a PowerShell provider.</span></span>

<span data-ttu-id="d1701-274">エクスポートされたコマンドは、エクスポート元の PSSession で暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="d1701-274">Exported commands run implicitly in the PSSession from which they were exported.</span></span> <span data-ttu-id="d1701-275">コマンドをリモートで実行する方法の詳細は、PowerShell によって完全に処理されます。</span><span class="sxs-lookup"><span data-stu-id="d1701-275">The details of running the commands remotely are handled entirely by PowerShell.</span></span> <span data-ttu-id="d1701-276">ローカル コマンドを実行するのと同じように、エクスポートしたコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d1701-276">You can run the exported commands just as you would run local commands.</span></span>

<span data-ttu-id="d1701-277">`Export-ModuleMember` は、エクスポートするモジュールの PSSession に関する情報をキャプチャして保存します。</span><span class="sxs-lookup"><span data-stu-id="d1701-277">`Export-ModuleMember` captures and saves information about the PSSession in the module that it exports.</span></span> <span data-ttu-id="d1701-278">モジュールをインポートするときに、コマンドのエクスポート元の PSSession が閉じられていて、同じコンピューターへのアクティブな PSSessions がない場合、モジュール内のコマンドは PSSession を再作成しようとします。</span><span class="sxs-lookup"><span data-stu-id="d1701-278">If the PSSession from which the commands were exported is closed when you import the module, and there are no active PSSessions to the same computer, the commands in the module attempt to recreate the PSSession.</span></span> <span data-ttu-id="d1701-279">PSSession を再作成しようとして失敗した場合、エクスポートされたコマンドは実行されません。</span><span class="sxs-lookup"><span data-stu-id="d1701-279">If attempts to recreate the PSSession fail, the exported commands will not run.</span></span>

<span data-ttu-id="d1701-280">モジュールでキャプチャして保存するセッション情報には、 `Export-ModuleMember` ユーザー設定変数で指定したセッションオプションや、、、 `$PSSessionOption` **SessionOption** `New-PSSession` `Enter-PSSession` またはコマンドレットの sessionoption パラメーターを使用したセッションオプションは含まれません `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="d1701-280">The session information that `Export-ModuleMember` captures and saves in the module does not include session options, such as those that you specify in the `$PSSessionOption` preference variable or by using the **SessionOption** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlets.</span></span> <span data-ttu-id="d1701-281">モジュールをインポートするときに、元の PSSession が閉じている場合、モジュールは同じコンピューターに対する別の利用可能な PSSession を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1701-281">If the original PSSession is closed when you import the module, the module will use another PSSession to the same computer, if one is available.</span></span> <span data-ttu-id="d1701-282">インポートされたコマンドを正しい構成のセッションで実行するには、必要なオプションで PSSession を作成してから、モジュールをインポートするようにしてください。</span><span class="sxs-lookup"><span data-stu-id="d1701-282">To enable the imported commands to run in a correctly configured session, create a PSSession with the options that you want before you import the module.</span></span>

<span data-ttu-id="d1701-283">エクスポートするコマンドを見つけるには、コマンドレットを使用して `Export-PSSession` `Invoke-Command` `Get-Command` PSSession でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d1701-283">To find the commands to export, `Export-PSSession` uses the `Invoke-Command` cmdlet to run a `Get-Command` command in the PSSession.</span></span> <span data-ttu-id="d1701-284">コマンドの書式設定データを取得して保存するには、コマンドレットとコマンドレットを使用し `Get-FormatData` `Export-FormatData` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-284">To get and save formatting data for the commands, it uses the `Get-FormatData` and `Export-FormatData` cmdlets.</span></span> <span data-ttu-id="d1701-285">コマンドを実行すると、、、、およびからのエラーメッセージが表示される場合があり `Invoke-Command` `Get-Command` `Get-FormatData` `Export-FormatData` `Export-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="d1701-285">You might see error messages from `Invoke-Command`, `Get-Command`, `Get-FormatData`, and `Export-FormatData` when you run an `Export-PSSession` command.</span></span> <span data-ttu-id="d1701-286">また、、、 `Export-PSSession` `Get-Command` `Get-FormatData` `Select-Object` 、およびコマンドレットを含まないセッションからコマンドをエクスポートすることはできません `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="d1701-286">Also, `Export-PSSession` cannot export commands from a session that does not include the `Get-Command`, `Get-FormatData`, `Select-Object`, and `Get-Help` cmdlets.</span></span>

<span data-ttu-id="d1701-287">`Export-PSSession` コマンドレットを使用して、 `Write-Progress` コマンドの進行状況を表示します。</span><span class="sxs-lookup"><span data-stu-id="d1701-287">`Export-PSSession` uses the `Write-Progress` cmdlet to display the progress of the command.</span></span> <span data-ttu-id="d1701-288">コマンドが実行中の場合、進行状況バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1701-288">You might see the progress bar while the command is running.</span></span>

<span data-ttu-id="d1701-289">エクスポートされたコマンドには、ユーザー インターフェイスを備えたプログラム (たとえば、メモ帳) を起動することができないなど、他のリモート コマンドと同じ制限があります。</span><span class="sxs-lookup"><span data-stu-id="d1701-289">Exported commands have the same limitations as other remote commands, including the inability to start a program with a user interface, such as Notepad.</span></span>

<span data-ttu-id="d1701-290">PowerShell プロファイルは PSSessions では実行されないため、プロファイルによってセッションに追加されたコマンドはでは使用できません `Export-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="d1701-290">Because PowerShell profiles are not run in PSSessions, the commands that a profile adds to a session are not available to `Export-PSSession`.</span></span> <span data-ttu-id="d1701-291">プロファイルからコマンドをエクスポートするには、コマンドを使用して、コマンドをエクスポートする前に、コマンドを使用し `Invoke-Command` て PSSession でプロファイルを手動で実行します。</span><span class="sxs-lookup"><span data-stu-id="d1701-291">To export commands from a profile, use an `Invoke-Command` command to run the profile in the PSSession manually before exporting commands.</span></span>

<span data-ttu-id="d1701-292">`Export-PSSession`コマンドが書式設定データをインポートしない場合でも、を作成するモジュールには書式設定ファイルが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1701-292">The module that `Export-PSSession` creates might include a formatting file, even if the command does not import formatting data.</span></span> <span data-ttu-id="d1701-293">コマンドで書式データがインポートされない場合、作成される書式ファイルに書式データは含まれません。</span><span class="sxs-lookup"><span data-stu-id="d1701-293">If the command does not import formatting data, any formatting files that are created will not contain formatting data.</span></span>

## <span data-ttu-id="d1701-294">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d1701-294">RELATED LINKS</span></span>

[<span data-ttu-id="d1701-295">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="d1701-295">about_Command_Precedence</span></span>](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md)

[<span data-ttu-id="d1701-296">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="d1701-296">about_PSSessions</span></span>](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[<span data-ttu-id="d1701-297">about_PSSnapins</span><span class="sxs-lookup"><span data-stu-id="d1701-297">about_PSSnapins</span></span>](/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1)

[<span data-ttu-id="d1701-298">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="d1701-298">about_Remote_Requirements</span></span>](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)

[<span data-ttu-id="d1701-299">Import-Module</span><span class="sxs-lookup"><span data-stu-id="d1701-299">Import-Module</span></span>](../Microsoft.PowerShell.Core/Import-Module.md)

[<span data-ttu-id="d1701-300">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="d1701-300">Import-PSSession</span></span>](Import-PSSession.md)

[<span data-ttu-id="d1701-301">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="d1701-301">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="d1701-302">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="d1701-302">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="d1701-303">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="d1701-303">New-PSSessionOption</span></span>](../Microsoft.PowerShell.Core/New-PSSessionOption.md)

[<span data-ttu-id="d1701-304">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="d1701-304">Remove-PSSession</span></span>](../Microsoft.PowerShell.Core/Remove-PSSession.md)
