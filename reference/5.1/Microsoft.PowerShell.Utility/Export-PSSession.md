---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-PSSession
ms.openlocfilehash: 11533a9b127dc6d088258392c0e142bfbe5c070c
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388027"
---
# <span data-ttu-id="5eeb4-103">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="5eeb4-103">Export-PSSession</span></span>

## <span data-ttu-id="5eeb4-104">概要</span><span class="sxs-lookup"><span data-stu-id="5eeb4-104">SYNOPSIS</span></span>

<span data-ttu-id="5eeb4-105">別のセッションからコマンドをエクスポートし、PowerShell モジュールに保存します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-105">Exports commands from another session and saves them in a PowerShell module.</span></span>

## <span data-ttu-id="5eeb4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5eeb4-106">SYNTAX</span></span>

```
Export-PSSession [-Session] <PSSession> [-OutputModule] <string> [[-CommandName] <string[]>]
 [[-FormatTypeName] <string[]>] [-Force] [-Encoding <string>] [-AllowClobber]
 [-ArgumentList <Object[]>] [-CommandType <CommandTypes>] [-Module <string[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-Certificate <X509Certificate2>]
 [<CommonParameters>]
```

## <span data-ttu-id="5eeb4-107">Description</span><span class="sxs-lookup"><span data-stu-id="5eeb4-107">DESCRIPTION</span></span>

<span data-ttu-id="5eeb4-108">コマンド `Export-PSSession` レットは、ローカルコンピューターまたはリモートコンピューター上の別の powershell セッション (PSSession) からコマンドレット、関数、エイリアス、およびその他のコマンドの種類を取得し、powershell モジュールに保存します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-108">The `Export-PSSession` cmdlet gets cmdlets, functions, aliases, and other command types from another PowerShell session (PSSession) on a local or remote computer and saves them in a PowerShell module.</span></span> <span data-ttu-id="5eeb4-109">モジュールのコマンドを現在のセッションに追加するには、コマンドレットを使用し `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-109">To add the commands from the module to the current session, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="5eeb4-110">`Import-PSSession`別の PSSession から現在のセッションにコマンドをインポートするとは異なり、は `Export-PSSession` モジュールにコマンドを保存します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-110">Unlike `Import-PSSession`, which imports commands from another PSSession into the current session, `Export-PSSession` saves the commands in a module.</span></span> <span data-ttu-id="5eeb4-111">コマンドは、現在のセッションにはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-111">The commands are not imported into the current session.</span></span>

<span data-ttu-id="5eeb4-112">コマンドをエクスポートするには、コマンドレットを使用して、 `New-PSSession` エクスポートするコマンドを含む PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-112">To export commands, use the `New-PSSession` cmdlet to create a PSSession that has the commands that you want to export.</span></span> <span data-ttu-id="5eeb4-113">次に、 `Export-PSSession` コマンドレットを使用してコマンドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-113">Then use the `Export-PSSession` cmdlet to export the commands.</span></span>

<span data-ttu-id="5eeb4-114">コマンド名の競合を防ぐため、の既定で `Export-PSSession` は、現在のセッションに存在するコマンドを除き、すべてのコマンドがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-114">To prevent command name conflicts, the default for `Export-PSSession` is to export all commands, except for commands that exist in the current session.</span></span> <span data-ttu-id="5eeb4-115">**CommandName** パラメーターを使用して、エクスポートするコマンドを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-115">You can use the **CommandName** parameter to specify the commands to export.</span></span>

<span data-ttu-id="5eeb4-116">`Export-PSSession`コマンドレットでは、PowerShell の暗黙的なリモート処理機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-116">The `Export-PSSession` cmdlet uses the implicit remoting feature of PowerShell.</span></span> <span data-ttu-id="5eeb4-117">現在のセッションにコマンドをインポートすると、元のセッションまたは元のコンピューターの同様のセッションで、コマンドが暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-117">When you import commands into the current session, they run implicitly in the original session or in a similar session on the originating computer.</span></span>

## <span data-ttu-id="5eeb4-118">例</span><span class="sxs-lookup"><span data-stu-id="5eeb4-118">EXAMPLES</span></span>

### <span data-ttu-id="5eeb4-119">例 1: PSSession からコマンドをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5eeb4-119">Example 1: Export commands from a PSSession</span></span>

<span data-ttu-id="5eeb4-120">この例では、ローカルコンピューターから Server01 コンピューターに新しい PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-120">This example creates a new PSSession from the local computer to the Server01 computer.</span></span> <span data-ttu-id="5eeb4-121">現在のセッションに存在するコマンドを除くすべてのコマンドは、ローカルコンピューター上の Server01 という名前のモジュールにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-121">All of the commands, except those that exist in the current session, are exported to the module named Server01 on the local computer.</span></span> <span data-ttu-id="5eeb4-122">エクスポートには、コマンドの書式設定データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-122">The export includes the formatting data for the commands.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01
Export-PSSession -Session $S -OutputModule Server01
```

<span data-ttu-id="5eeb4-123">この `New-PSSession` コマンドは、Server01 コンピューター上に PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-123">The `New-PSSession` command creates a PSSession on the Server01 computer.</span></span> <span data-ttu-id="5eeb4-124">PSSession は変数に格納され `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-124">The PSSession is stored in the `$S` variable.</span></span> <span data-ttu-id="5eeb4-125">この `Export-PSSession` コマンドは、 `$S` 変数のコマンドをエクスポートし、Server01 モジュールにデータを書式設定します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-125">The `Export-PSSession` command exports the `$S` variable's commands and formatting data into the Server01 module.</span></span>

### <span data-ttu-id="5eeb4-126">例 2: Get コマンドと Set コマンドをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5eeb4-126">Example 2: Export the Get and Set commands</span></span>

<span data-ttu-id="5eeb4-127">この例では、 `Get` サーバーからすべてのコマンドとコマンドをエクスポートし `Set` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-127">This example exports all of the `Get` and `Set` commands from a server.</span></span>

```powershell
$S = New-PSSession -ConnectionUri https://exchange.microsoft.com/mailbox -Credential exchangeadmin01@hotmail.com -Authentication Negotiate
Export-PSSession -Session $S -Module exch* -CommandName Get-*, Set-* -FormatTypeName * -OutputModule $PSHOME\Modules\Exchange -Encoding ASCII
```

<span data-ttu-id="5eeb4-128">これらのコマンドは `Get` 、 `Set` リモートコンピューター上の Microsoft exchange Server スナップインからローカルコンピューター上のディレクトリの Exchange モジュールに、コマンドとコマンドをエクスポートし `$PSHOME\Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-128">These commands export the `Get` and `Set` commands from a Microsoft Exchange Server snap-in on a remote computer to an Exchange module in the `$PSHOME\Modules` directory on the local computer.</span></span>
<span data-ttu-id="5eeb4-129">ディレクトリにモジュールを配置 `$PSHOME\Modules` すると、コンピューターのすべてのユーザーがそのモジュールにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-129">Placing the module in the `$PSHOME\Modules` directory makes it accessible to all users of the computer.</span></span>

### <span data-ttu-id="5eeb4-130">例 3: リモートコンピューターからコマンドをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5eeb4-130">Example 3: Export commands from a remote computer</span></span>

<span data-ttu-id="5eeb4-131">この例では、リモートコンピューター上の PSSession からコマンドレットをエクスポートし、ローカルコンピューター上のモジュールに保存します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-131">This example exports cmdlets from a PSSession on a remote computer and saves them in a module on the local computer.</span></span> <span data-ttu-id="5eeb4-132">モジュールのコマンドレットが現在のセッションに追加され、使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-132">The cmdlets from the module are added to the current session so that they can be used.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01 -Credential Server01\User01
Export-PSSession -Session $S -OutputModule TestCmdlets -Type Cmdlet -CommandName *test* -FormatTypeName *
Remove-PSSession $S
Import-Module TestCmdlets
Get-Help Test*
Test-Files
```

<span data-ttu-id="5eeb4-133">`New-PSSession`このコマンドは、Server01 コンピューター上に PSSession を作成し、変数に保存し `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-133">The `New-PSSession` command creates a PSSession on the Server01 computer and saves it in the `$S` variable.</span></span> <span data-ttu-id="5eeb4-134">コマンドは、 `Export-PSSession` の PSSession から `$S` ローカルコンピューター上の testcmdlets モジュールへのテストで名前が始まるコマンドレットをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-134">The `Export-PSSession` command exports the cmdlets whose names begin with Test from the PSSession in `$S` to the TestCmdlets module on the local computer.</span></span>

<span data-ttu-id="5eeb4-135">`Remove-PSSession`コマンドレットでは、の PSSession を `$S` 現在のセッションから削除します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-135">The `Remove-PSSession` cmdlet deletes the PSSession in `$S` from the current session.</span></span> <span data-ttu-id="5eeb4-136">このコマンドは、セッションからインポートされたコマンドを使用するために PSSession をアクティブにする必要がないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-136">This command shows that the PSSession need not be active to use the commands that were imported from the session.</span></span> <span data-ttu-id="5eeb4-137">コマンドレットでは、 `Import-Module` testcmdlets モジュール内のコマンドレットを現在のセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-137">The `Import-Module` cmdlet adds the cmdlets in the TestCmdlets module to the current session.</span></span> <span data-ttu-id="5eeb4-138">コマンドは、任意のセッションでいつでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-138">The command can be run in any session at any time.</span></span>

<span data-ttu-id="5eeb4-139">`Get-Help`コマンドレットは、名前が Test で始まるコマンドレットのヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-139">The `Get-Help` cmdlet gets help for cmdlets whose names begin with Test.</span></span> <span data-ttu-id="5eeb4-140">モジュール内のコマンドを現在のセッションに追加した後は、コマンドレットとコマンドレットを使用して、インポートした `Get-Help` `Get-Command` コマンドについて学習できます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-140">After the commands in a module are added to the current session, you can use the `Get-Help` and `Get-Command` cmdlets to learn about the imported commands.</span></span> <span data-ttu-id="5eeb4-141">`Test-Files`コマンドレットが Server01 コンピューターからエクスポートされ、セッションに追加されました。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-141">The `Test-Files` cmdlet was exported from the Server01 computer and added to the session.</span></span> <span data-ttu-id="5eeb4-142">`Test-Files`コマンドレットは、コマンドがインポートされたコンピューター上のリモートセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-142">The `Test-Files` cmdlet runs in a remote session on the computer from which the command was imported.</span></span> <span data-ttu-id="5eeb4-143">PowerShell は、TestCmdlets モジュールに格納されている情報からセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-143">PowerShell creates a session from information that is stored in the TestCmdlets module.</span></span>

### <span data-ttu-id="5eeb4-144">例 4: 現在のセッションでコマンドを Export および上書きする</span><span class="sxs-lookup"><span data-stu-id="5eeb4-144">Example 4: Export and clobber commands in the current session</span></span>

<span data-ttu-id="5eeb4-145">この例では、変数に格納されているコマンドを現在のセッションにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-145">This example exports commands that are stored in a variable into the current session.</span></span>

```powershell
Export-PSSession -Session $S -AllowClobber -OutputModule AllCommands
```

<span data-ttu-id="5eeb4-146">この `Export-PSSession` コマンドは、変数内の PSSession から現在のセッションにすべてのコマンドおよびすべての書式設定データをエクスポートし `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-146">This `Export-PSSession` command exports all commands and all formatting data from the PSSession in the `$S` variable into the current session.</span></span> <span data-ttu-id="5eeb4-147">**AllowClobber** パラメーターには、現在のセッションのコマンドと同じ名前のコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-147">The **AllowClobber** parameter includes commands with the same names as commands in the current session.</span></span>

### <span data-ttu-id="5eeb4-148">例 5: 閉じた PSSession からコマンドをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5eeb4-148">Example 5: Export commands from a closed PSSession</span></span>

<span data-ttu-id="5eeb4-149">この例では、エクスポートされたコマンドを作成した PSSession が閉じているときに、特別なオプションを使用してエクスポートされたコマンドを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-149">This example shows how to run the exported commands with special options when the PSSession that created the exported commands is closed.</span></span>

<span data-ttu-id="5eeb4-150">モジュールをインポートするときに元のリモートセッションが閉じている場合、モジュールは、元のコンピューターに接続している開いているリモートセッションを使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-150">If the original remote session is closed when a module is imported, the module will use any open remote session that connects to the originating computer.</span></span> <span data-ttu-id="5eeb4-151">発信元のコンピューターに現在のセッションがない場合は、モジュールによってセッションが再確立されます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-151">If there is no current session to the originating computer, the module will reestablish a session.</span></span>

<span data-ttu-id="5eeb4-152">リモートセッションで特別なオプションを指定してエクスポートされたコマンドを実行するには、モジュールをインポートする前に、これらのオプションを使用してリモートセッションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-152">To run exported commands with special options in a remote session, you must create a remote session with those options before you import the module.</span></span> <span data-ttu-id="5eeb4-153">`New-PSSession` **Sessionoption** パラメーターを指定してコマンドレットを使用する</span><span class="sxs-lookup"><span data-stu-id="5eeb4-153">Use the `New-PSSession` cmdlet with the **SessionOption** parameter</span></span>

```powershell
$Options = New-PSSessionOption -NoMachineProfile
$S = New-PSSession -ComputerName Server01 -SessionOption $Options
Export-PSSession -Session $S -OutputModule Server01
Remove-PSSession $S
New-PSSession -ComputerName Server01 -SessionOption $Options
Import-Module Server01
```

<span data-ttu-id="5eeb4-154">コマンドレットでは、 `New-PSSessionOption` **Pssessionoption** オブジェクトを作成し、そのオブジェクトを変数に保存し `$Options` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-154">The `New-PSSessionOption` cmdlet creates a **PSSessionOption** object, and it saves the object in the `$Options` variable.</span></span> <span data-ttu-id="5eeb4-155">この `New-PSSession` コマンドは、Server01 コンピューター上に PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-155">The `New-PSSession` command creates a PSSession on the Server01 computer.</span></span>
<span data-ttu-id="5eeb4-156">**Sessionoption** パラメーターは、に格納されているオブジェクトを使用し `$Options` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-156">The **SessionOption** parameter uses the object stored in `$Options`.</span></span> <span data-ttu-id="5eeb4-157">セッションは変数に格納され `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-157">The session is stored in the `$S` variable.</span></span>

<span data-ttu-id="5eeb4-158">コマンド `Export-PSSession` レットは、の PSSession から `$S` Server01 モジュールにコマンドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-158">The `Export-PSSession` cmdlet exports commands from the PSSession in `$S` to the Server01 module.</span></span>
<span data-ttu-id="5eeb4-159">この `Remove-PSSession` コマンドレットは、変数内の PSSession を削除し `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-159">The `Remove-PSSession` cmdlet deletes the PSSession in the `$S` variable.</span></span>

<span data-ttu-id="5eeb4-160">コマンドレットでは、 `New-PSSession` Server01 コンピューターに接続する新しい PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-160">The `New-PSSession` cmdlet creates a new PSSession that connects to the Server01 computer.</span></span> <span data-ttu-id="5eeb4-161">**Sessionoption** パラメーターは、に格納されているオブジェクトを使用し `$Options` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-161">The **SessionOption** parameter uses the object stored in `$Options`.</span></span> <span data-ttu-id="5eeb4-162">`Import-Module`コマンドレットは、Server01 モジュールからコマンドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-162">The `Import-Module` cmdlet imports the commands from the Server01 module.</span></span> <span data-ttu-id="5eeb4-163">モジュール内のコマンドは、Server01 コンピューター上の PSSession で実行されます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-163">The commands in the module are run in the PSSession on the Server01 computer.</span></span>

## <span data-ttu-id="5eeb4-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5eeb4-164">PARAMETERS</span></span>

### <span data-ttu-id="5eeb4-165">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="5eeb4-165">-AllowClobber</span></span>

<span data-ttu-id="5eeb4-166">現在のセッションのコマンドと同じ名前でも、指定されたコマンドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-166">Exports the specified commands, even if they have the same names as commands in the current session.</span></span>

<span data-ttu-id="5eeb4-167">現在のセッションのコマンドと同じ名前のコマンドをエクスポートすると、エクスポートされたコマンドは元のコマンドを非表示にしたり置き換えたりします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-167">If you export a command with the same name as a command in the current session, the exported command hides or replaces the original commands.</span></span> <span data-ttu-id="5eeb4-168">詳細については、「[about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md)」(コマンドの優先順位について) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-168">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span></span>

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

### <span data-ttu-id="5eeb4-169">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="5eeb4-169">-ArgumentList</span></span>

<span data-ttu-id="5eeb4-170">指定された引数 (パラメーター値) を使用して生成されたコマンドのバリアントをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-170">Exports the variant of the command that results from using the specified arguments (parameter values).</span></span>

<span data-ttu-id="5eeb4-171">たとえば、証明書内のコマンドのバリアントをエクスポートするには `Get-Item` (Cert:)の PSSession のドライブに `$S` 、「」と入力 `Export-PSSession -Session $S -Command Get-Item -ArgumentList cert:` します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-171">For example, to export the variant of the `Get-Item` command in the certificate (Cert:) drive in the PSSession in `$S`, type `Export-PSSession -Session $S -Command Get-Item -ArgumentList cert:`.</span></span>

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

### <span data-ttu-id="5eeb4-172">-証明書</span><span class="sxs-lookup"><span data-stu-id="5eeb4-172">-Certificate</span></span>

<span data-ttu-id="5eeb4-173">を作成するモジュールで、フォーマットファイル (\* .Format.ps1xml) またはスクリプトモジュールファイル (hbase-runner.psm1) の署名に使用されるクライアント証明書を指定し `Export-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-173">Specifies the client certificate that is used to sign the format files (\*.Format.ps1xml) or script module files (.psm1) in the module that `Export-PSSession` creates.</span></span> <span data-ttu-id="5eeb4-174">証明書が格納されている変数を入力するか、証明書を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-174">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="5eeb4-175">証明書を検索するには、コマンドレットを使用する `Get-PfxCertificate` か、 `Get-ChildItem` 証明書 (Cert:) のコマンドレットを使用します。駆動.</span><span class="sxs-lookup"><span data-stu-id="5eeb4-175">To find a certificate, use the `Get-PfxCertificate` cmdlet or use the `Get-ChildItem` cmdlet in the Certificate (Cert:) drive.</span></span> <span data-ttu-id="5eeb4-176">証明書が無効な場合、または証明書に十分な権限がない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-176">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="5eeb4-177">-CommandName</span><span class="sxs-lookup"><span data-stu-id="5eeb4-177">-CommandName</span></span>

<span data-ttu-id="5eeb4-178">指定した名前または名前パターンのコマンドのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-178">Exports only the commands with the specified names or name patterns.</span></span> <span data-ttu-id="5eeb4-179">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-179">Wildcards are permitted.</span></span> <span data-ttu-id="5eeb4-180">**CommandName** またはそのエイリアスである **Name** を使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-180">Use **CommandName** or its alias, **Name**.</span></span>

<span data-ttu-id="5eeb4-181">既定では、は、 `Export-PSSession` 現在のセッションのコマンドと同じ名前を持つコマンドを除き、PSSession からすべてのコマンドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-181">By default, `Export-PSSession` exports all commands from the PSSession except for commands that have the same names as commands in the current session.</span></span> <span data-ttu-id="5eeb4-182">これにより、現在のセッションのコマンドによってコマンドが非表示になったり置き換えられたりするのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-182">This prevents commands from being hidden or replaced by commands in the current session.</span></span> <span data-ttu-id="5eeb4-183">他のコマンドを表示または置換するコマンドも含めて、すべてのコマンドをエクスポートするには、 **AllowClobber** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-183">To export all commands, even those that hide or replace other commands, use the **AllowClobber** parameter.</span></span>

<span data-ttu-id="5eeb4-184">**CommandName** パラメーターを使用する場合、 **formattypename** パラメーターを使用しない限り、コマンドの書式設定ファイルはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-184">If you use the **CommandName** parameter, the formatting files for the commands are not exported unless you use the **FormatTypeName** parameter.</span></span> <span data-ttu-id="5eeb4-185">同様に、 **Formattypename** パラメーターを使用する場合、 **CommandName** パラメーターを使用しない限り、コマンドはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-185">Similarly, if you use the **FormatTypeName** parameter, no commands are exported unless you use the **CommandName** parameter.</span></span>

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

### <span data-ttu-id="5eeb4-186">-CommandType</span><span class="sxs-lookup"><span data-stu-id="5eeb4-186">-CommandType</span></span>

<span data-ttu-id="5eeb4-187">指定された型のコマンド オブジェクトのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-187">Exports only the specified types of command objects.</span></span> <span data-ttu-id="5eeb4-188">**CommandType** またはそのエイリアスの **Type** を使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-188">Use **CommandType** or its alias, **Type**.</span></span>

<span data-ttu-id="5eeb4-189">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-189">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="5eeb4-190">エイリアス.</span><span class="sxs-lookup"><span data-stu-id="5eeb4-190">Alias.</span></span> <span data-ttu-id="5eeb4-191">現在のセッションのすべての PowerShell エイリアス。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-191">All PowerShell aliases in the current session.</span></span>
- <span data-ttu-id="5eeb4-192">すべて。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-192">All.</span></span> <span data-ttu-id="5eeb4-193">すべてのコマンドの型。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-193">All command types.</span></span> <span data-ttu-id="5eeb4-194">これは、と同じです `Get-Command -Name *` 。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-194">It is the equivalent of `Get-Command -Name *`.</span></span>
- <span data-ttu-id="5eeb4-195">アプリケーション をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-195">Application.</span></span> <span data-ttu-id="5eeb4-196">Path 環境変数 () に一覧表示されているパス内の PowerShell ファイル以外のすべてのファイル ( `$env:path` .txt、.exe、.dll ファイルなど)。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-196">All files other than PowerShell files in paths listed in the Path environment variable (`$env:path`), including .txt, .exe, and .dll files.</span></span>
- <span data-ttu-id="5eeb4-197">コマンドレット.</span><span class="sxs-lookup"><span data-stu-id="5eeb4-197">Cmdlet.</span></span> <span data-ttu-id="5eeb4-198">現在のセッションのコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-198">The cmdlets in the current session.</span></span> <span data-ttu-id="5eeb4-199">コマンドレットが既定値です。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-199">Cmdlet is the default.</span></span>
- <span data-ttu-id="5eeb4-200">構成。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-200">Configuration.</span></span> <span data-ttu-id="5eeb4-201">PowerShell 構成。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-201">A PowerShell configuration.</span></span> <span data-ttu-id="5eeb4-202">詳細については、「 [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-202">For more information, see [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span></span>
- <span data-ttu-id="5eeb4-203">ExternalScript。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-203">ExternalScript.</span></span> <span data-ttu-id="5eeb4-204">Path 環境変数 () に示されているパス内のすべての ps1 ファイル。 `$env:path`</span><span class="sxs-lookup"><span data-stu-id="5eeb4-204">All .ps1 files in the paths listed in the Path environment variable (`$env:path`).</span></span>
- <span data-ttu-id="5eeb4-205">フィルターと関数。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-205">Filter and Function.</span></span> <span data-ttu-id="5eeb4-206">すべての PowerShell 関数。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-206">All PowerShell functions.</span></span>
- <span data-ttu-id="5eeb4-207">スクリプティング。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-207">Script.</span></span> <span data-ttu-id="5eeb4-208">現在のセッションのスクリプト ブロック。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-208">Script blocks in the current session.</span></span>
- <span data-ttu-id="5eeb4-209">稟議.</span><span class="sxs-lookup"><span data-stu-id="5eeb4-209">Workflow.</span></span> <span data-ttu-id="5eeb4-210">PowerShell ワークフロー。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-210">A PowerShell workflow.</span></span> <span data-ttu-id="5eeb4-211">詳細については、「 [about_Workflows](../PSWorkflow/About/about_Workflows.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-211">For more information, see [about_Workflows](../PSWorkflow/About/about_Workflows.md).</span></span>

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

### <span data-ttu-id="5eeb4-212">-Encoding</span><span class="sxs-lookup"><span data-stu-id="5eeb4-212">-Encoding</span></span>

<span data-ttu-id="5eeb4-213">ターゲット ファイルのエンコードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-213">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="5eeb4-214">既定値は `UTF8` です。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-214">The default value is `UTF8`.</span></span>

<span data-ttu-id="5eeb4-215">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-215">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="5eeb4-216">`ASCII` ASCII (7 ビット) 文字セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-216">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="5eeb4-217">`BigEndianUnicode` は、ビッグエンディアンのバイト順で UTF-16 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-217">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="5eeb4-218">`Default` システムのアクティブなコードページに対応するエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-218">`Default` Uses the encoding that corresponds to the system's active code page.</span></span>
- <span data-ttu-id="5eeb4-219">`OEM` は、システムの現在の OEM コードページに対応するエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-219">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="5eeb4-220">`Unicode` は、リトルエンディアンのバイト順で UTF-16 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-220">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="5eeb4-221">`UTF7` UTF-7 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-221">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="5eeb4-222">`UTF8` UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-222">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="5eeb4-223">`UTF32` は、リトルエンディアンのバイト順で 32 UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-223">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: UTF8
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5eeb4-224">-Force</span><span class="sxs-lookup"><span data-stu-id="5eeb4-224">-Force</span></span>

<span data-ttu-id="5eeb4-225">ファイルが読み取り専用属性を持つ場合でも、1 つ以上の既存の出力ファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-225">Overwrites one or more existing output files, even if the file has the read-only attribute.</span></span>

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

### <span data-ttu-id="5eeb4-226">-FormatTypeName</span><span class="sxs-lookup"><span data-stu-id="5eeb4-226">-FormatTypeName</span></span>

<span data-ttu-id="5eeb4-227">指定された Microsoft .NET Framework 型の書式設定命令をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-227">Exports formatting instructions only for the specified Microsoft .NET Framework types.</span></span> <span data-ttu-id="5eeb4-228">型名を入力します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-228">Enter the type names.</span></span> <span data-ttu-id="5eeb4-229">既定では、は、 `Export-PSSession` .NET Framework の名前空間に含まれてい **System.Management.Automation** ないすべての型の書式設定命令をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-229">By default, `Export-PSSession` exports formatting instructions for all .NET Framework types that are not in the **System.Management.Automation** namespace.</span></span>

<span data-ttu-id="5eeb4-230">このパラメーターの値は、コマンドがインポートされるセッション内のコマンドによって返される型の名前である必要があり `Get-FormatData` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-230">The value of this parameter must be the name of a type that is returned by a `Get-FormatData` command in the session from which the commands are being imported.</span></span> <span data-ttu-id="5eeb4-231">リモートセッションのすべての書式設定データを取得するには、「」と入力 `*` します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-231">To get all of the formatting data in the remote session, type `*`.</span></span>

<span data-ttu-id="5eeb4-232">**Formattypename** パラメーターを使用する場合、 **CommandName** パラメーターを使用しない限り、コマンドはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-232">If you use the **FormatTypeName** parameter, no commands are exported unless you use the **CommandName** parameter.</span></span>

<span data-ttu-id="5eeb4-233">**CommandName** パラメーターを使用する場合、 **formattypename** パラメーターを使用しない限り、コマンドの書式設定ファイルはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-233">If you use the **CommandName** parameter, the formatting files for the commands are not exported unless you use the **FormatTypeName** parameter.</span></span>

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

### <span data-ttu-id="5eeb4-234">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="5eeb4-234">-FullyQualifiedModule</span></span>

<span data-ttu-id="5eeb4-235">**Modul特定** のオブジェクトの形式で指定された名前を持つモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-235">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span> <span data-ttu-id="5eeb4-236">「 [Modulの認識コンストラクター (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_)」の「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-236">See the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="5eeb4-237">たとえば、 **FullyQualifiedModule** パラメーターは、次のいずれかの形式で指定されたモジュール名を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-237">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in either of these formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="5eeb4-238">**ModuleName** と **ModuleVersion** は必須ですが、 **Guid** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-238">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span> <span data-ttu-id="5eeb4-239">**モジュール** パラメーターと同じコマンドで **FullyQualifiedModule** パラメーターを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-239">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="5eeb4-240">2つのパラメーターは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-240">the two parameters are mutually exclusive.</span></span>

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

### <span data-ttu-id="5eeb4-241">-モジュール</span><span class="sxs-lookup"><span data-stu-id="5eeb4-241">-Module</span></span>

<span data-ttu-id="5eeb4-242">指定した PowerShell スナップインおよびモジュールのコマンドのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-242">Exports only the commands in the specified PowerShell snap-ins and modules.</span></span> <span data-ttu-id="5eeb4-243">スナップインとモジュールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-243">Enter the snap-in and module names.</span></span> <span data-ttu-id="5eeb4-244">ワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-244">Wildcards are not permitted.</span></span>

<span data-ttu-id="5eeb4-245">詳細については、「」および about_PSSnapins を参照してください `Import-Module` 。 [about_PSSnapins](../Microsoft.PowerShell.Core/About/about_PSSnapins.md)</span><span class="sxs-lookup"><span data-stu-id="5eeb4-245">For more information, see `Import-Module` and [about_PSSnapins](../Microsoft.PowerShell.Core/About/about_PSSnapins.md).</span></span>

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

### <span data-ttu-id="5eeb4-246">-OutputModule</span><span class="sxs-lookup"><span data-stu-id="5eeb4-246">-OutputModule</span></span>

<span data-ttu-id="5eeb4-247">によって作成されたモジュールのパスと名前 (省略可能) を指定し `Export-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-247">Specifies an optional path and name for the module created by `Export-PSSession`.</span></span> <span data-ttu-id="5eeb4-248">既定のパスは、`$home\Documents\WindowsPowerShell\Modules` です。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-248">The default path is `$home\Documents\WindowsPowerShell\Modules`.</span></span> <span data-ttu-id="5eeb4-249">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-249">This parameter is required.</span></span>

<span data-ttu-id="5eeb4-250">モジュールサブディレクトリまたはが作成したファイルが `Export-PSSession` 既に存在する場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-250">If the module subdirectory or any of the files that `Export-PSSession` creates already exist, the command fails.</span></span> <span data-ttu-id="5eeb4-251">既存のファイルを上書きするには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-251">To overwrite existing files, use the **Force** parameter.</span></span>

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

### <span data-ttu-id="5eeb4-252">-セッション</span><span class="sxs-lookup"><span data-stu-id="5eeb4-252">-Session</span></span>

<span data-ttu-id="5eeb4-253">コマンドのエクスポート元の PSSession を指定します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-253">Specifies the PSSession from which the commands are exported.</span></span> <span data-ttu-id="5eeb4-254">セッションオブジェクトを含む変数、またはコマンドなどのセッションオブジェクトを取得するコマンドを入力し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-254">Enter a variable that contains a session object or a command that gets a session object, such as a `Get-PSSession` command.</span></span> <span data-ttu-id="5eeb4-255">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-255">This parameter is required.</span></span>

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

### <span data-ttu-id="5eeb4-256">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5eeb4-256">CommonParameters</span></span>

<span data-ttu-id="5eeb4-257">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-257">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5eeb4-258">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-258">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5eeb4-259">入力</span><span class="sxs-lookup"><span data-stu-id="5eeb4-259">INPUTS</span></span>

### <span data-ttu-id="5eeb4-260">なし</span><span class="sxs-lookup"><span data-stu-id="5eeb4-260">None</span></span>

<span data-ttu-id="5eeb4-261">パイプを使用してオブジェクトをにパイプすることはできません `Export-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-261">You cannot pipe objects to `Export-PSSession`.</span></span>

## <span data-ttu-id="5eeb4-262">出力</span><span class="sxs-lookup"><span data-stu-id="5eeb4-262">OUTPUTS</span></span>

### <span data-ttu-id="5eeb4-263">システム. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="5eeb4-263">System.IO.FileInfo</span></span>

<span data-ttu-id="5eeb4-264">`Export-PSSession` 作成したモジュールを構成するファイルの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-264">`Export-PSSession` returns a list of files that comprise the module that it created.</span></span>

## <span data-ttu-id="5eeb4-265">注</span><span class="sxs-lookup"><span data-stu-id="5eeb4-265">NOTES</span></span>

<span data-ttu-id="5eeb4-266">`Export-PSSession` は、PowerShell リモート処理インフラストラクチャに依存しています。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-266">`Export-PSSession` relies on the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="5eeb4-267">このコマンドレットを使用するには、リモート用にコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-267">To use this cmdlet, the computer must be configured for remoting.</span></span> <span data-ttu-id="5eeb4-268">詳細については、「[about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-268">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="5eeb4-269">を使用して `Export-PSSession` PowerShell プロバイダーをエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-269">You cannot use `Export-PSSession` to export a PowerShell provider.</span></span>

<span data-ttu-id="5eeb4-270">エクスポートされたコマンドは、エクスポート元の PSSession で暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-270">Exported commands run implicitly in the PSSession from which they were exported.</span></span> <span data-ttu-id="5eeb4-271">コマンドをリモートで実行する方法の詳細は、PowerShell によって完全に処理されます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-271">The details of running the commands remotely are handled entirely by PowerShell.</span></span> <span data-ttu-id="5eeb4-272">ローカル コマンドを実行するのと同じように、エクスポートしたコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-272">You can run the exported commands just as you would run local commands.</span></span>

<span data-ttu-id="5eeb4-273">`Export-ModuleMember` は、エクスポートするモジュールの PSSession に関する情報をキャプチャして保存します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-273">`Export-ModuleMember` captures and saves information about the PSSession in the module that it exports.</span></span> <span data-ttu-id="5eeb4-274">モジュールをインポートするときに、コマンドのエクスポート元の PSSession が閉じられていて、同じコンピューターへのアクティブな PSSessions がない場合、モジュール内のコマンドは PSSession を再作成しようとします。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-274">If the PSSession from which the commands were exported is closed when you import the module, and there are no active PSSessions to the same computer, the commands in the module attempt to recreate the PSSession.</span></span> <span data-ttu-id="5eeb4-275">PSSession を再作成しようとして失敗した場合、エクスポートされたコマンドは実行されません。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-275">If attempts to recreate the PSSession fail, the exported commands will not run.</span></span>

<span data-ttu-id="5eeb4-276">モジュールでキャプチャして保存するセッション情報には、 `Export-ModuleMember` ユーザー設定変数で指定したセッションオプションや、、、 `$PSSessionOption` **SessionOption** `New-PSSession` `Enter-PSSession` またはコマンドレットの sessionoption パラメーターを使用したセッションオプションは含まれません `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-276">The session information that `Export-ModuleMember` captures and saves in the module does not include session options, such as those that you specify in the `$PSSessionOption` preference variable or by using the **SessionOption** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlets.</span></span> <span data-ttu-id="5eeb4-277">モジュールをインポートするときに、元の PSSession が閉じている場合、モジュールは同じコンピューターに対する別の利用可能な PSSession を使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-277">If the original PSSession is closed when you import the module, the module will use another PSSession to the same computer, if one is available.</span></span> <span data-ttu-id="5eeb4-278">インポートされたコマンドを正しい構成のセッションで実行するには、必要なオプションで PSSession を作成してから、モジュールをインポートするようにしてください。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-278">To enable the imported commands to run in a correctly configured session, create a PSSession with the options that you want before you import the module.</span></span>

<span data-ttu-id="5eeb4-279">エクスポートするコマンドを見つけるには、コマンドレットを使用して `Export-PSSession` `Invoke-Command` `Get-Command` PSSession でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-279">To find the commands to export, `Export-PSSession` uses the `Invoke-Command` cmdlet to run a `Get-Command` command in the PSSession.</span></span> <span data-ttu-id="5eeb4-280">コマンドの書式設定データを取得して保存するには、コマンドレットとコマンドレットを使用し `Get-FormatData` `Export-FormatData` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-280">To get and save formatting data for the commands, it uses the `Get-FormatData` and `Export-FormatData` cmdlets.</span></span> <span data-ttu-id="5eeb4-281">コマンドを実行すると、、、、およびからのエラーメッセージが表示される場合があり `Invoke-Command` `Get-Command` `Get-FormatData` `Export-FormatData` `Export-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-281">You might see error messages from `Invoke-Command`, `Get-Command`, `Get-FormatData`, and `Export-FormatData` when you run an `Export-PSSession` command.</span></span> <span data-ttu-id="5eeb4-282">また、、、 `Export-PSSession` `Get-Command` `Get-FormatData` `Select-Object` 、およびコマンドレットを含まないセッションからコマンドをエクスポートすることはできません `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-282">Also, `Export-PSSession` cannot export commands from a session that does not include the `Get-Command`, `Get-FormatData`, `Select-Object`, and `Get-Help` cmdlets.</span></span>

<span data-ttu-id="5eeb4-283">`Export-PSSession` コマンドレットを使用して、 `Write-Progress` コマンドの進行状況を表示します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-283">`Export-PSSession` uses the `Write-Progress` cmdlet to display the progress of the command.</span></span> <span data-ttu-id="5eeb4-284">コマンドが実行中の場合、進行状況バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-284">You might see the progress bar while the command is running.</span></span>

<span data-ttu-id="5eeb4-285">エクスポートされたコマンドには、ユーザー インターフェイスを備えたプログラム (たとえば、メモ帳) を起動することができないなど、他のリモート コマンドと同じ制限があります。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-285">Exported commands have the same limitations as other remote commands, including the inability to start a program with a user interface, such as Notepad.</span></span>

<span data-ttu-id="5eeb4-286">PowerShell プロファイルは PSSessions では実行されないため、プロファイルによってセッションに追加されたコマンドはでは使用できません `Export-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-286">Because PowerShell profiles are not run in PSSessions, the commands that a profile adds to a session are not available to `Export-PSSession`.</span></span> <span data-ttu-id="5eeb4-287">プロファイルからコマンドをエクスポートするには、コマンドを使用して、コマンドをエクスポートする前に、コマンドを使用し `Invoke-Command` て PSSession でプロファイルを手動で実行します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-287">To export commands from a profile, use an `Invoke-Command` command to run the profile in the PSSession manually before exporting commands.</span></span>

<span data-ttu-id="5eeb4-288">`Export-PSSession`コマンドが書式設定データをインポートしない場合でも、を作成するモジュールには書式設定ファイルが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-288">The module that `Export-PSSession` creates might include a formatting file, even if the command does not import formatting data.</span></span> <span data-ttu-id="5eeb4-289">コマンドで書式データがインポートされない場合、作成される書式ファイルに書式データは含まれません。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-289">If the command does not import formatting data, any formatting files that are created will not contain formatting data.</span></span>

## <span data-ttu-id="5eeb4-290">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5eeb4-290">RELATED LINKS</span></span>

[<span data-ttu-id="5eeb4-291">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="5eeb4-291">about_Command_Precedence</span></span>](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md)

[<span data-ttu-id="5eeb4-292">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="5eeb4-292">about_PSSessions</span></span>](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[<span data-ttu-id="5eeb4-293">about_PSSnapins</span><span class="sxs-lookup"><span data-stu-id="5eeb4-293">about_PSSnapins</span></span>](../Microsoft.PowerShell.Core/About/about_PSSnapins.md)

[<span data-ttu-id="5eeb4-294">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="5eeb4-294">about_Remote_Requirements</span></span>](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)

[<span data-ttu-id="5eeb4-295">Import-Module</span><span class="sxs-lookup"><span data-stu-id="5eeb4-295">Import-Module</span></span>](../Microsoft.PowerShell.Core/Import-Module.md)

[<span data-ttu-id="5eeb4-296">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="5eeb4-296">Import-PSSession</span></span>](Import-PSSession.md)

[<span data-ttu-id="5eeb4-297">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="5eeb4-297">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="5eeb4-298">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="5eeb4-298">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="5eeb4-299">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="5eeb4-299">New-PSSessionOption</span></span>](../Microsoft.PowerShell.Core/New-PSSessionOption.md)

[<span data-ttu-id="5eeb4-300">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="5eeb4-300">Remove-PSSession</span></span>](../Microsoft.PowerShell.Core/Remove-PSSession.md)
