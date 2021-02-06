---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-location?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Location
ms.openlocfilehash: ec6f69d1d4a0b382ceec26b9409d01501edb814f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602207"
---
# <span data-ttu-id="f10a7-102">Set-Location</span><span class="sxs-lookup"><span data-stu-id="f10a7-102">Set-Location</span></span>

## <span data-ttu-id="f10a7-103">概要</span><span class="sxs-lookup"><span data-stu-id="f10a7-103">SYNOPSIS</span></span>
<span data-ttu-id="f10a7-104">現在の作業場所を、指定された場所に設定します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-104">Sets the current working location to a specified location.</span></span>

## <span data-ttu-id="f10a7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f10a7-105">SYNTAX</span></span>

### <span data-ttu-id="f10a7-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="f10a7-106">Path (Default)</span></span>

```
Set-Location [[-Path] <String>] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="f10a7-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f10a7-107">LiteralPath</span></span>

```
Set-Location -LiteralPath <String> [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="f10a7-108">スタック</span><span class="sxs-lookup"><span data-stu-id="f10a7-108">Stack</span></span>

```
Set-Location [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## <span data-ttu-id="f10a7-109">Description</span><span class="sxs-lookup"><span data-stu-id="f10a7-109">DESCRIPTION</span></span>

<span data-ttu-id="f10a7-110">コマンドレットでは、 `Set-Location` 作業場所を指定した場所に設定します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-110">The `Set-Location` cmdlet sets the working location to a specified location.</span></span> <span data-ttu-id="f10a7-111">この場所には、ディレクトリ、サブディレクトリ、レジストリの場所、または任意のプロバイダーパスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-111">That location could be a directory, a subdirectory, a registry location, or any provider path.</span></span>

<span data-ttu-id="f10a7-112">PowerShell 6.2 では、 `-` `+` **Path** パラメーターの値としておよびのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="f10a7-112">PowerShell 6.2 added support for `-` and `+` as a values for the **Path** parameter.</span></span> <span data-ttu-id="f10a7-113">PowerShell では、およびでアクセスできる最新の20個の場所の履歴が保持され `-` `+` ます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-113">PowerShell maintains a history of the last 20 locations that can be accessed with `-` and `+`.</span></span> <span data-ttu-id="f10a7-114">このリストは、 **Stackname** パラメーターを使用してアクセスされる場所スタックからは独立しています。</span><span class="sxs-lookup"><span data-stu-id="f10a7-114">This list is independent from the location stack that is accessed using the **StackName** parameter.</span></span>

## <span data-ttu-id="f10a7-115">例</span><span class="sxs-lookup"><span data-stu-id="f10a7-115">EXAMPLES</span></span>

### <span data-ttu-id="f10a7-116">例 1: 現在の場所を設定する</span><span class="sxs-lookup"><span data-stu-id="f10a7-116">Example 1: Set the current location</span></span>

```
PS C:\> Set-Location -Path "HKLM:\"
PS HKLM:\>
```

<span data-ttu-id="f10a7-117">このコマンドは、現在の場所をドライブのルートに設定し `HKLM:` ます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-117">This command sets the current location to the root of the `HKLM:` drive.</span></span>

### <span data-ttu-id="f10a7-118">例 2: 現在の場所を設定し、その場所を表示する</span><span class="sxs-lookup"><span data-stu-id="f10a7-118">Example 2: Set the current location and display that location</span></span>

```
PS C:\> Set-Location -Path "Env:\" -PassThru
```

```Output
Path
----
Env:\

PS Env:\>
```

<span data-ttu-id="f10a7-119">このコマンドは、現在の場所をドライブのルートに設定し `Env:` ます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-119">This command sets the current location to the root of the `Env:` drive.</span></span> <span data-ttu-id="f10a7-120">**PassThru** パラメーターを使用して、場所を表す **pathinfo** オブジェクトを返すように PowerShell に指示し `Env:\` ます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-120">It uses the **PassThru** parameter to direct PowerShell to return a **PathInfo** object that represents the `Env:\` location.</span></span>

### <span data-ttu-id="f10a7-121">例 3: 場所を C: ドライブの現在の場所に設定する</span><span class="sxs-lookup"><span data-stu-id="f10a7-121">Example 3: Set location to the current location in the C: drive</span></span>

```powershell
PS C:\Windows\> Set-Location HKLM:\
PS HKLM:\> Set-Location C:
PS C:\Windows\>
```

<span data-ttu-id="f10a7-122">最初のコマンドは、レジストリプロバイダーのドライブのルートに場所を設定し `HKLM:` ます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-122">The first command sets the location to the root of the `HKLM:` drive in the Registry provider.</span></span>
<span data-ttu-id="f10a7-123">2番目のコマンドは、場所を FileSystem プロバイダーのドライブの現在の場所に設定し `C:` ます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-123">The second command sets the location to the current location of the `C:` drive in the FileSystem provider.</span></span>
<span data-ttu-id="f10a7-124">(円記号を使用せずに) 形式でドライブ名を指定すると、コマンドレットによって `<DriveName>:` 場所が PSDrive 内の現在の場所に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-124">When the drive name is specified in the form `<DriveName>:` (without backslash), the cmdlet sets the location to the current location in the PSDrive.</span></span>
<span data-ttu-id="f10a7-125">PSDrive use コマンドで現在の場所を取得し `Get-Location -PSDrive <DriveName>` ます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-125">To get the current location in the PSDrive use `Get-Location -PSDrive <DriveName>` command.</span></span>

### <span data-ttu-id="f10a7-126">例 4: 現在の場所を名前付きスタックに設定する</span><span class="sxs-lookup"><span data-stu-id="f10a7-126">Example 4: Set the current location to a named stack</span></span>

```
PS C:\> Push-Location -Path 'C:\Program Files\PowerShell\' -StackName "Paths"
PS C:\Program Files\PowerShell\> Set-Location -StackName "Paths"
PS C:\Program Files\PowerShell\> Get-Location -Stack
```

```Output
Path
----
C:\
```

<span data-ttu-id="f10a7-127">最初のコマンドは、現在の場所をパススタックに追加します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-127">The first command adds the current location to the Paths stack.</span></span>
<span data-ttu-id="f10a7-128">2番目のコマンドは、パスの場所スタックを現在の場所スタックにします。</span><span class="sxs-lookup"><span data-stu-id="f10a7-128">The second command makes the Paths location stack the current location stack.</span></span>
<span data-ttu-id="f10a7-129">3番目のコマンドは、現在の場所スタック内の場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-129">The third command displays the locations in the current location stack.</span></span>

<span data-ttu-id="f10a7-130">`*-Location`コマンドレットは、コマンドで別の場所スタックが指定されていない限り、現在の場所スタックを使用します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-130">The `*-Location` cmdlets use the current location stack unless a different location stack is specified in the command.</span></span> <span data-ttu-id="f10a7-131">場所スタックの詳細については、「 [注](#notes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f10a7-131">For information about location stacks, see the [Notes](#notes).</span></span>

### <span data-ttu-id="f10a7-132">例 5: またはを使用して場所の履歴を移動する `+``-`</span><span class="sxs-lookup"><span data-stu-id="f10a7-132">Example 5: Navigate location history using `+` or `-`</span></span>

```
PS C:\> Set-Location -Path $env:SystemRoot
PS C:\Windows> Set-Location -Path Cert:\
PS Cert:\> Set-Location -Path HKLM:\
PS HKLM:\>

# Navigate back through the history using "-"
PS HKLM:\> Set-Location -Path -
PS Cert:\> Set-Location -Path -
PS C:\Windows>

# Navigate using the Set-Location alias "cd" and the implicit positional Path parameter
PS C:\Windows> cd -
PS C:\> cd +
PS C:\Windows> cd +
PS Cert:\>
```

<span data-ttu-id="f10a7-133">エイリアスを使用 `cd -` すると、 `cd +` ターミナルでの場所の履歴を簡単に移動できます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-133">Using the alias, `cd -` or `cd +` is an easy way to navigate through your location history while in your terminal.</span></span> <span data-ttu-id="f10a7-134">を使用した移動の詳細につい `-` / `+` ては、 **Path** パラメーターを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f10a7-134">For more information on navigating with `-`/`+`, see the **Path** parameter.</span></span>

## <span data-ttu-id="f10a7-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f10a7-135">PARAMETERS</span></span>

### <span data-ttu-id="f10a7-136">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f10a7-136">-LiteralPath</span></span>

<span data-ttu-id="f10a7-137">場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-137">Specifies a path of the location.</span></span> <span data-ttu-id="f10a7-138">**LiteralPath** パラメーターの値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-138">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="f10a7-139">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="f10a7-139">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="f10a7-140">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-140">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="f10a7-141">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="f10a7-141">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f10a7-142">-PassThru</span><span class="sxs-lookup"><span data-stu-id="f10a7-142">-PassThru</span></span>

<span data-ttu-id="f10a7-143">位置を表す **Pathinfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-143">Returns a **PathInfo** object that represents the location.</span></span> <span data-ttu-id="f10a7-144">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="f10a7-144">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="f10a7-145">-Path</span><span class="sxs-lookup"><span data-stu-id="f10a7-145">-Path</span></span>

<span data-ttu-id="f10a7-146">新しい作業場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-146">Specify the path of a new working location.</span></span> <span data-ttu-id="f10a7-147">パスが指定されていない場合、既定では `Set-Location` 現在のユーザーのホームディレクトリになります。</span><span class="sxs-lookup"><span data-stu-id="f10a7-147">If no path is provided, `Set-Location` defaults to the current user's home directory.</span></span> <span data-ttu-id="f10a7-148">ワイルドカードを使用すると、コマンドレットは、ワイルドカードパターンに一致する最初のパスを選択します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-148">When wildcards are used, the cmdlet chooses the first path that matches the wildcard pattern.</span></span>

<span data-ttu-id="f10a7-149">PowerShell では、最後に設定した20個の場所の履歴が保持されます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-149">PowerShell keeps a history of the last 20 locations you have set.</span></span> <span data-ttu-id="f10a7-150">**Path** パラメーターの値が文字の場合 `-` 、新しい作業場所は履歴内の前の作業場所 (存在する場合) になります。</span><span class="sxs-lookup"><span data-stu-id="f10a7-150">If the **Path** parameter value is the `-` character, then the new working location will be the previous working location in history (if it exists).</span></span> <span data-ttu-id="f10a7-151">同様に、値が文字の場合、 `+` 新しい作業場所は履歴内の次の作業場所 (存在する場合) になります。</span><span class="sxs-lookup"><span data-stu-id="f10a7-151">Similarly, if the value is the `+` character, then the new working location will be the next working location in history (if it exists).</span></span> <span data-ttu-id="f10a7-152">これは、およびを使用する場合と似ていますが、履歴はスタックではなくリストであり、 `Pop-Location` `Push-Location` 暗黙的に追跡され、手動で制御される点が異なります。</span><span class="sxs-lookup"><span data-stu-id="f10a7-152">This is similar to using `Pop-Location` and `Push-Location` except that the history is a list, not a stack, and is implicitly tracked, not manually controlled.</span></span> <span data-ttu-id="f10a7-153">現在、履歴一覧を表示する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="f10a7-153">Currently, there is no way to view the history list.</span></span>

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

### <span data-ttu-id="f10a7-154">-StackName</span><span class="sxs-lookup"><span data-stu-id="f10a7-154">-StackName</span></span>

<span data-ttu-id="f10a7-155">このコマンドレットによって現在の場所スタックが作成される既存の場所スタック名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-155">Specifies the existing location stack name that this cmdlet makes the current location stack.</span></span> <span data-ttu-id="f10a7-156">場所スタック名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-156">Enter a location stack name.</span></span> <span data-ttu-id="f10a7-157">名前のない既定の場所スタックを示すに `$null` は、または空の文字列 () を入力 `""` します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-157">To indicate the unnamed default location stack, type `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="f10a7-158">`*-Location` **Stackname** パラメーターを使用して別のスタックを指定しない限り、コマンドレットは現在のスタックに対して動作します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-158">The `*-Location` cmdlets act on the current stack unless you use the **StackName** parameter to specify a different stack.</span></span> <span data-ttu-id="f10a7-159">場所スタックの詳細については、「 [注](#notes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f10a7-159">For more information about location stacks, see the [Notes](#notes).</span></span>

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

### <span data-ttu-id="f10a7-160">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f10a7-160">CommonParameters</span></span>

<span data-ttu-id="f10a7-161">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f10a7-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f10a7-162">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f10a7-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f10a7-163">入力</span><span class="sxs-lookup"><span data-stu-id="f10a7-163">INPUTS</span></span>

### <span data-ttu-id="f10a7-164">System.String</span><span class="sxs-lookup"><span data-stu-id="f10a7-164">System.String</span></span>

<span data-ttu-id="f10a7-165">パイプを使用してパスを含む文字列をこのコマンドレットに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-165">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="f10a7-166">出力</span><span class="sxs-lookup"><span data-stu-id="f10a7-166">OUTPUTS</span></span>

### <span data-ttu-id="f10a7-167">なし、システムの管理.......................... PathInfoStack</span><span class="sxs-lookup"><span data-stu-id="f10a7-167">None, System.Management.Automation.PathInfo, System.Management.Automation.PathInfoStack</span></span>

<span data-ttu-id="f10a7-168">**PassThru** パラメーターを指定しない限り、このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="f10a7-168">This cmdlet does not generate any output unless you specify the **PassThru** parameter.</span></span> <span data-ttu-id="f10a7-169">**パススルー** と **Path** または **LiteralPath** を使用すると、新しい場所を表す **pathinfo** オブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-169">Using **PassThru** with **Path** or **LiteralPath** generates a **PathInfo** object that represents the new location.</span></span> <span data-ttu-id="f10a7-170">**Stackname** と共に **PassThru** を使用すると、新しいスタックコンテキストを表す **pathinfostack** オブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-170">Using **PassThru** with **StackName** generates a **PathInfoStack** object representing the new stack context.</span></span>

## <span data-ttu-id="f10a7-171">注</span><span class="sxs-lookup"><span data-stu-id="f10a7-171">NOTES</span></span>

<span data-ttu-id="f10a7-172">PowerShell では、プロセスごとに複数の実行空間がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-172">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="f10a7-173">各実行空間には、独自の _現在のディレクトリ_ があります。</span><span class="sxs-lookup"><span data-stu-id="f10a7-173">Each runspace has its own _current directory_.</span></span>
<span data-ttu-id="f10a7-174">これはと同じではありません `[System.Environment]::CurrentDirectory` 。</span><span class="sxs-lookup"><span data-stu-id="f10a7-174">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="f10a7-175">この動作は、明示的なディレクトリパスを指定せずに、.NET Api を呼び出したり、ネイティブアプリケーションを実行したりするときに問題になることがあります。</span><span class="sxs-lookup"><span data-stu-id="f10a7-175">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="f10a7-176">場所のコマンドレットでプロセス全体の現在のディレクトリが設定されていても、別の実行空間によっていつでも変更される可能性があるため、このディレクトリに依存することはできません。</span><span class="sxs-lookup"><span data-stu-id="f10a7-176">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="f10a7-177">現在の実行空間に固有の現在の作業ディレクトリを使用して、パスベースの操作を実行するには、location コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f10a7-177">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="f10a7-178">`Set-Location`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="f10a7-178">The `Set-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="f10a7-179">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-179">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="f10a7-180">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f10a7-180">For more information, see [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).</span></span>

<span data-ttu-id="f10a7-181">スタックとは、最後に追加された項目だけにアクセスできる、後入れ先出しのリストです。</span><span class="sxs-lookup"><span data-stu-id="f10a7-181">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="f10a7-182">使用した順序でスタックに項目を追加し、その後、逆の順序で使用するために項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-182">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="f10a7-183">PowerShell では、プロバイダーの場所を場所スタックに格納できます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-183">PowerShell lets you store provider locations in location stacks.</span></span> <span data-ttu-id="f10a7-184">PowerShell によって、名前のない既定の場所スタックが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-184">PowerShell creates an unnamed default location stack.</span></span> <span data-ttu-id="f10a7-185">複数の名前付きの場所スタックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-185">You can create multiple named location stacks.</span></span> <span data-ttu-id="f10a7-186">スタック名を指定しない場合、PowerShell は現在の場所スタックを使用します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-186">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="f10a7-187">既定では、名前のない既定の場所は現在の場所スタックですが、コマンドレットを使用して `Set-Location` 現在の場所スタックを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-187">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="f10a7-188">場所スタックを管理するには、次のように `*-Location` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f10a7-188">To manage location stacks, use the `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="f10a7-189">場所スタックに場所を追加するには、コマンドレットを使用し `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-189">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="f10a7-190">場所スタックから場所を取得するには、コマンドレットを使用し `Pop-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-190">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="f10a7-191">現在の場所スタック内の場所を表示するには、コマンドレットの **stack** パラメーターを使用し `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-191">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span> <span data-ttu-id="f10a7-192">名前付きの場所スタック内の場所を表示するには、の **Stackname** パラメーターを使用し `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-192">To display the locations in a named location stack, use the **StackName** parameter of `Get-Location`.</span></span>

- <span data-ttu-id="f10a7-193">新しい場所スタックを作成するには、の **Stackname** パラメーターを使用し `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-193">To create a new location stack, use the **StackName** parameter of `Push-Location`.</span></span> <span data-ttu-id="f10a7-194">存在しないスタックを指定すると、によっ `Push-Location` てスタックが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-194">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="f10a7-195">場所スタックを現在の場所スタックにするには、の **Stackname** パラメーターを使用し `Set-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-195">To make a location stack the current location stack, use the **StackName** parameter of `Set-Location`.</span></span>

<span data-ttu-id="f10a7-196">名前のない既定の場所スタックは、現在の場所スタックになっている場合にだけ、完全にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-196">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="f10a7-197">名前付きの場所スタックを現在の場所スタックにすると、またはコマンドレットを使用して `Push-Location` `Pop-Location` 既定のスタックから項目を追加または取得したり、コマンドレットを使用して名前のないスタック内の場所を表示したりすることができなくなり `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-197">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="f10a7-198">名前のないスタックを現在のスタックにするには、コマンドレットの **Stackname** パラメーター `Set-Location` の値を `$null` または空の文字列 () に設定し `""` ます。</span><span class="sxs-lookup"><span data-stu-id="f10a7-198">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

## <span data-ttu-id="f10a7-199">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f10a7-199">RELATED LINKS</span></span>

[<span data-ttu-id="f10a7-200">Get-Location</span><span class="sxs-lookup"><span data-stu-id="f10a7-200">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="f10a7-201">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="f10a7-201">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="f10a7-202">Push-Location</span><span class="sxs-lookup"><span data-stu-id="f10a7-202">Push-Location</span></span>](Push-Location.md)

