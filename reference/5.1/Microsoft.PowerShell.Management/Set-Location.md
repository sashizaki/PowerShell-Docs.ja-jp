---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-location?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Location
ms.openlocfilehash: 06b1596366c9c9e20857b55aa9a17342bab07028
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "93219552"
---
# <span data-ttu-id="95fa9-103">Set-Location</span><span class="sxs-lookup"><span data-stu-id="95fa9-103">Set-Location</span></span>

## <span data-ttu-id="95fa9-104">概要</span><span class="sxs-lookup"><span data-stu-id="95fa9-104">SYNOPSIS</span></span>
<span data-ttu-id="95fa9-105">現在の作業場所を、指定された場所に設定します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-105">Sets the current working location to a specified location.</span></span>

## <span data-ttu-id="95fa9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="95fa9-106">SYNTAX</span></span>

### <span data-ttu-id="95fa9-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="95fa9-107">Path (Default)</span></span>

```
Set-Location [[-Path] <String>] [-PassThru] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="95fa9-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="95fa9-108">LiteralPath</span></span>

```
Set-Location -LiteralPath <String> [-PassThru] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="95fa9-109">スタック</span><span class="sxs-lookup"><span data-stu-id="95fa9-109">Stack</span></span>

```
Set-Location [-PassThru] [-StackName <String>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="95fa9-110">Description</span><span class="sxs-lookup"><span data-stu-id="95fa9-110">DESCRIPTION</span></span>

<span data-ttu-id="95fa9-111">コマンドレットでは、 `Set-Location` 作業場所を指定した場所に設定します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-111">The `Set-Location` cmdlet sets the working location to a specified location.</span></span> <span data-ttu-id="95fa9-112">この場所には、ディレクトリ、サブディレクトリ、レジストリの場所、または任意のプロバイダーパスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-112">That location could be a directory, a subdirectory, a registry location, or any provider path.</span></span>

<span data-ttu-id="95fa9-113">**Stackname** パラメーターを使用して、名前付きの場所スタックを現在の場所スタックにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-113">You can also use the **StackName** parameter to make a named location stack the current location stack.</span></span> <span data-ttu-id="95fa9-114">場所スタックの詳細については、「注」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95fa9-114">For more information about location stacks, see the Notes.</span></span>

## <span data-ttu-id="95fa9-115">例</span><span class="sxs-lookup"><span data-stu-id="95fa9-115">EXAMPLES</span></span>

### <span data-ttu-id="95fa9-116">例 1: 現在の場所を設定する</span><span class="sxs-lookup"><span data-stu-id="95fa9-116">Example 1: Set the current location</span></span>

```powershell
PS C:\> Set-Location -Path "HKLM:\"
```

```output
PS HKLM:\>
```

<span data-ttu-id="95fa9-117">このコマンドは、現在の場所をドライブのルートに設定し `HKLM:` ます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-117">This command sets the current location to the root of the `HKLM:` drive.</span></span>

### <span data-ttu-id="95fa9-118">例 2: 現在の場所を設定し、その場所を表示する</span><span class="sxs-lookup"><span data-stu-id="95fa9-118">Example 2: Set the current location and display that location</span></span>

```powershell
PS C:\> Set-Location -Path "Env:\" -PassThru
```

```output
Path
----
Env:\

PS Env:\>
```

<span data-ttu-id="95fa9-119">このコマンドは、現在の場所をドライブのルートに設定し `Env:` ます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-119">This command sets the current location to the root of the `Env:` drive.</span></span> <span data-ttu-id="95fa9-120">**PassThru** パラメーターを使用して、場所を表す **pathinfo** オブジェクトを返すように PowerShell に指示し `Env:\` ます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-120">It uses the **PassThru** parameter to direct PowerShell to return a **PathInfo** object that represents the `Env:\` location.</span></span>

### <span data-ttu-id="95fa9-121">例 3: 場所を C: ドライブの現在の場所に設定する</span><span class="sxs-lookup"><span data-stu-id="95fa9-121">Example 3: Set location to the current location in the C: drive</span></span>

```powershell
PS C:\Windows\> Set-Location HKLM:\
PS HKLM:\> Set-Location C:
PS C:\Windows\>
```

<span data-ttu-id="95fa9-122">最初のコマンドは、レジストリプロバイダーのドライブのルートに場所を設定し `HKLM:` ます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-122">The first command sets the location to the root of the `HKLM:` drive in the Registry provider.</span></span>
<span data-ttu-id="95fa9-123">2番目のコマンドは、場所を FileSystem プロバイダーのドライブの現在の場所に設定し `C:` ます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-123">The second command sets the location to the current location of the `C:` drive in the FileSystem provider.</span></span>
<span data-ttu-id="95fa9-124">(円記号を使用せずに) 形式でドライブ名を指定すると、コマンドレットによって `<DriveName>:` 場所が PSDrive 内の現在の場所に設定されます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-124">When the drive name is specified in the form `<DriveName>:` (without backslash), the cmdlet sets the location to the current location in the PSDrive.</span></span>
<span data-ttu-id="95fa9-125">PSDrive use コマンドで現在の場所を取得し `Get-Location -PSDrive <DriveName>` ます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-125">To get the current location in the PSDrive use `Get-Location -PSDrive <DriveName>` command.</span></span>

### <span data-ttu-id="95fa9-126">例 4: 現在の場所を名前付きスタックに設定する</span><span class="sxs-lookup"><span data-stu-id="95fa9-126">Example 4: Set the current location to a named stack</span></span>

```powershell
PS C:\> Push-Location -Path 'C:\Program Files\PowerShell\' -StackName "Paths"
PS C:\Program Files\PowerShell\> Set-Location -StackName "Paths"
PS C:\Program Files\PowerShell\> Get-Location -Stack
```

```Output
Path
----
C:\
```

<span data-ttu-id="95fa9-127">最初のコマンドは、現在の場所をパススタックに追加します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-127">The first command adds the current location to the Paths stack.</span></span>
<span data-ttu-id="95fa9-128">2番目のコマンドは、パスの場所スタックを現在の場所スタックにします。</span><span class="sxs-lookup"><span data-stu-id="95fa9-128">The second command makes the Paths location stack the current location stack.</span></span>
<span data-ttu-id="95fa9-129">3番目のコマンドは、現在の場所スタック内の場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-129">The third command displays the locations in the current location stack.</span></span>

<span data-ttu-id="95fa9-130">`*-Location`コマンドレットは、コマンドで別の場所スタックが指定されていない限り、現在の場所スタックを使用します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-130">The `*-Location` cmdlets use the current location stack unless a different location stack is specified in the command.</span></span> <span data-ttu-id="95fa9-131">場所スタックの詳細については、「 [注](#notes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95fa9-131">For information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="95fa9-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="95fa9-132">PARAMETERS</span></span>

### <span data-ttu-id="95fa9-133">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="95fa9-133">-LiteralPath</span></span>

<span data-ttu-id="95fa9-134">場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-134">Specifies a path of the location.</span></span> <span data-ttu-id="95fa9-135">**LiteralPath** パラメーターの値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-135">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="95fa9-136">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="95fa9-136">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="95fa9-137">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-137">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="95fa9-138">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="95fa9-138">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="95fa9-139">単一引用符で囲んだ文字はエスケープ シーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="95fa9-139">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="95fa9-140">-PassThru</span><span class="sxs-lookup"><span data-stu-id="95fa9-140">-PassThru</span></span>

<span data-ttu-id="95fa9-141">位置を表す **Pathinfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-141">Returns a **PathInfo** object that represents the location.</span></span> <span data-ttu-id="95fa9-142">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="95fa9-142">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95fa9-143">-Path</span><span class="sxs-lookup"><span data-stu-id="95fa9-143">-Path</span></span>

<span data-ttu-id="95fa9-144">新しい作業場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-144">Specify the path of a new working location.</span></span> <span data-ttu-id="95fa9-145">パスが指定されていない場合、既定では `Set-Location` 現在のユーザーのホームディレクトリになります。</span><span class="sxs-lookup"><span data-stu-id="95fa9-145">If no path is provided, `Set-Location` defaults to the current user's home directory.</span></span> <span data-ttu-id="95fa9-146">ワイルドカードを使用すると、コマンドレットは、ワイルドカードパターンに一致する最初のパスを選択します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-146">When wildcards are used, the cmdlet chooses the first path that matches the wildcard pattern.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="95fa9-147">-StackName</span><span class="sxs-lookup"><span data-stu-id="95fa9-147">-StackName</span></span>

<span data-ttu-id="95fa9-148">このコマンドレットによって現在の場所スタックが作成される既存の場所スタック名を指定します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-148">Specifies the existing location stack name that this cmdlet makes the current location stack.</span></span> <span data-ttu-id="95fa9-149">場所スタック名を入力します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-149">Enter a location stack name.</span></span> <span data-ttu-id="95fa9-150">名前のない既定の場所スタックを示すに `$null` は、または空の文字列 () を入力 `""` します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-150">To indicate the unnamed default location stack, type `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="95fa9-151">`*-Location` **Stackname** パラメーターを使用して別のスタックを指定しない限り、コマンドレットは現在のスタックに対して動作します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-151">The `*-Location` cmdlets act on the current stack unless you use the **StackName** parameter to specify a different stack.</span></span>

```yaml
Type: System.String
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="95fa9-152">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="95fa9-152">-UseTransaction</span></span>

<span data-ttu-id="95fa9-153">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-153">Includes the command in the active transaction.</span></span>
<span data-ttu-id="95fa9-154">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="95fa9-154">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="95fa9-155">詳細については、「about_Transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95fa9-155">For more information, see about_Transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95fa9-156">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="95fa9-156">CommonParameters</span></span>

<span data-ttu-id="95fa9-157">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="95fa9-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="95fa9-158">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95fa9-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="95fa9-159">入力</span><span class="sxs-lookup"><span data-stu-id="95fa9-159">INPUTS</span></span>

### <span data-ttu-id="95fa9-160">System.String</span><span class="sxs-lookup"><span data-stu-id="95fa9-160">System.String</span></span>

<span data-ttu-id="95fa9-161">パイプを使用してパスを含む文字列をこのコマンドレットに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-161">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="95fa9-162">出力</span><span class="sxs-lookup"><span data-stu-id="95fa9-162">OUTPUTS</span></span>

### <span data-ttu-id="95fa9-163">なし、システムの管理.......................... PathInfoStack</span><span class="sxs-lookup"><span data-stu-id="95fa9-163">None, System.Management.Automation.PathInfo, System.Management.Automation.PathInfoStack</span></span>

<span data-ttu-id="95fa9-164">**PassThru** パラメーターを指定しない限り、このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="95fa9-164">This cmdlet does not generate any output unless you specify the **PassThru** parameter.</span></span> <span data-ttu-id="95fa9-165">**パススルー** と **Path** または **LiteralPath** を使用すると、新しい場所を表す **pathinfo** オブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-165">Using **PassThru** with **Path** or **LiteralPath** generates a **PathInfo** object that represents the new location.</span></span> <span data-ttu-id="95fa9-166">**Stackname** と共に **PassThru** を使用すると、新しいスタックコンテキストを表す **pathinfostack** オブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-166">Using **PassThru** with **StackName** generates a **PathInfoStack** object representing the new stack context.</span></span>

## <span data-ttu-id="95fa9-167">注</span><span class="sxs-lookup"><span data-stu-id="95fa9-167">NOTES</span></span>

<span data-ttu-id="95fa9-168">PowerShell では、プロセスごとに複数の実行空間がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-168">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="95fa9-169">各実行空間には、独自の _現在のディレクトリ_ があります。</span><span class="sxs-lookup"><span data-stu-id="95fa9-169">Each runspace has its own _current directory_.</span></span>
<span data-ttu-id="95fa9-170">これはと同じではありません `[System.Environment]::CurrentDirectory` 。</span><span class="sxs-lookup"><span data-stu-id="95fa9-170">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="95fa9-171">この動作は、明示的なディレクトリパスを指定せずに、.NET Api を呼び出したり、ネイティブアプリケーションを実行したりするときに問題になることがあります。</span><span class="sxs-lookup"><span data-stu-id="95fa9-171">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="95fa9-172">場所のコマンドレットでプロセス全体の現在のディレクトリが設定されていても、別の実行空間によっていつでも変更される可能性があるため、このディレクトリに依存することはできません。</span><span class="sxs-lookup"><span data-stu-id="95fa9-172">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="95fa9-173">現在の実行空間に固有の現在の作業ディレクトリを使用して、パスベースの操作を実行するには、location コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95fa9-173">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="95fa9-174">`Set-Location`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="95fa9-174">The `Set-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="95fa9-175">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="95fa9-176">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95fa9-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).</span></span>

<span data-ttu-id="95fa9-177">スタックとは、最後に追加された項目だけにアクセスできる、後入れ先出しのリストです。</span><span class="sxs-lookup"><span data-stu-id="95fa9-177">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="95fa9-178">使用した順序でスタックに項目を追加し、その後、逆の順序で使用するために項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-178">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="95fa9-179">PowerShell では、プロバイダーの場所を場所スタックに格納できます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-179">PowerShell lets you store provider locations in location stacks.</span></span> <span data-ttu-id="95fa9-180">PowerShell によって、名前のない既定の場所スタックが作成されます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-180">PowerShell creates an unnamed default location stack.</span></span> <span data-ttu-id="95fa9-181">複数の名前付きの場所スタックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-181">You can create multiple named location stacks.</span></span> <span data-ttu-id="95fa9-182">スタック名を指定しない場合、PowerShell は現在の場所スタックを使用します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-182">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="95fa9-183">既定では、名前のない既定の場所は現在の場所スタックですが、コマンドレットを使用して `Set-Location` 現在の場所スタックを変更できます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-183">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="95fa9-184">場所スタックを管理するには、次のように `*-Location` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="95fa9-184">To manage location stacks, use the `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="95fa9-185">場所スタックに場所を追加するには、コマンドレットを使用し `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-185">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="95fa9-186">場所スタックから場所を取得するには、コマンドレットを使用し `Pop-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-186">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="95fa9-187">現在の場所スタック内の場所を表示するには、コマンドレットの **stack** パラメーターを使用し `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-187">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span> <span data-ttu-id="95fa9-188">名前付きの場所スタック内の場所を表示するには、の **Stackname** パラメーターを使用し `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-188">To display the locations in a named location stack, use the **StackName** parameter of `Get-Location`.</span></span>

- <span data-ttu-id="95fa9-189">新しい場所スタックを作成するには、の **Stackname** パラメーターを使用し `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-189">To create a new location stack, use the **StackName** parameter of `Push-Location`.</span></span> <span data-ttu-id="95fa9-190">存在しないスタックを指定すると、によっ `Push-Location` てスタックが作成されます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-190">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="95fa9-191">場所スタックを現在の場所スタックにするには、の **Stackname** パラメーターを使用し `Set-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-191">To make a location stack the current location stack, use the **StackName** parameter of `Set-Location`.</span></span>

<span data-ttu-id="95fa9-192">名前のない既定の場所スタックは、現在の場所スタックになっている場合にだけ、完全にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-192">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="95fa9-193">名前付きの場所スタックを現在の場所スタックにすると、またはコマンドレットを使用して `Push-Location` `Pop-Location` 既定のスタックから項目を追加または取得したり、コマンドレットを使用して名前のないスタック内の場所を表示したりすることができなくなり `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-193">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="95fa9-194">名前のないスタックを現在のスタックにするには、コマンドレットの **Stackname** パラメーター `Set-Location` の値を `$null` または空の文字列 () に設定し `""` ます。</span><span class="sxs-lookup"><span data-stu-id="95fa9-194">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

## <span data-ttu-id="95fa9-195">関連リンク</span><span class="sxs-lookup"><span data-stu-id="95fa9-195">RELATED LINKS</span></span>

[<span data-ttu-id="95fa9-196">Get-Location</span><span class="sxs-lookup"><span data-stu-id="95fa9-196">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="95fa9-197">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="95fa9-197">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="95fa9-198">Push-Location</span><span class="sxs-lookup"><span data-stu-id="95fa9-198">Push-Location</span></span>](Push-Location.md)
