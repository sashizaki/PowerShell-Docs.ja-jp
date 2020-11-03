---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/push-location?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Push-Location
ms.openlocfilehash: abc40f3ae388a915c9df42d0c2df24f848e45e73
ms.sourcegitcommit: 01a1c253f48b61c943f6d6aca4e603118014015f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "93219184"
---
# <span data-ttu-id="643e6-103">Push-Location</span><span class="sxs-lookup"><span data-stu-id="643e6-103">Push-Location</span></span>

## <span data-ttu-id="643e6-104">概要</span><span class="sxs-lookup"><span data-stu-id="643e6-104">SYNOPSIS</span></span>
<span data-ttu-id="643e6-105">現在の場所を、場所スタックの最上部に追加します。</span><span class="sxs-lookup"><span data-stu-id="643e6-105">Adds the current location to the top of a location stack.</span></span>

## <span data-ttu-id="643e6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="643e6-106">SYNTAX</span></span>

### <span data-ttu-id="643e6-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="643e6-107">Path (Default)</span></span>

```
Push-Location [[-Path] <String>] [-PassThru] [-StackName <String>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="643e6-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="643e6-108">LiteralPath</span></span>

```
Push-Location [-LiteralPath <String>] [-PassThru] [-StackName <String>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="643e6-109">Description</span><span class="sxs-lookup"><span data-stu-id="643e6-109">DESCRIPTION</span></span>

<span data-ttu-id="643e6-110">`Push-Location`コマンドレットは、現在の場所を場所スタックに追加 ("プッシュ") します。</span><span class="sxs-lookup"><span data-stu-id="643e6-110">The `Push-Location` cmdlet adds ("pushes") the current location onto a location stack.</span></span> <span data-ttu-id="643e6-111">パスを指定すると、は `Push-Location` 現在の場所を場所スタックにプッシュし、現在の場所をパスで指定された場所に変更します。</span><span class="sxs-lookup"><span data-stu-id="643e6-111">If you specify a path, `Push-Location` pushes the current location onto a location stack and then changes the current location to the location specified by the path.</span></span> <span data-ttu-id="643e6-112">コマンドレットを使用して `Pop-Location` 、場所スタックから場所を取得できます。</span><span class="sxs-lookup"><span data-stu-id="643e6-112">You can use the `Pop-Location` cmdlet to get locations from the location stack.</span></span>

<span data-ttu-id="643e6-113">既定では、コマンドレットは現在の場所を `Push-Location` 現在の場所スタックにプッシュしますが、 **stackname** パラメーターを使用して別の場所スタックを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="643e6-113">By default, the `Push-Location` cmdlet pushes the current location onto the current location stack, but you can use the **StackName** parameter to specify an alternate location stack.</span></span> <span data-ttu-id="643e6-114">スタックが存在しない場合は、に `Push-Location` よって作成されます。</span><span class="sxs-lookup"><span data-stu-id="643e6-114">If the stack does not exist, `Push-Location` creates it.</span></span>

<span data-ttu-id="643e6-115">場所スタックの詳細については、「 [注](#notes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="643e6-115">For more information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="643e6-116">例</span><span class="sxs-lookup"><span data-stu-id="643e6-116">EXAMPLES</span></span>

### <span data-ttu-id="643e6-117">例 1</span><span class="sxs-lookup"><span data-stu-id="643e6-117">Example 1</span></span>

<span data-ttu-id="643e6-118">この例では、現在の場所を既定の場所スタックにプッシュし、その場所をに変更し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="643e6-118">This example pushes the current location onto the default location stack and then changes the location to `C:\Windows`.</span></span>

```
PS C:\> Push-Location C:\Windows
```

### <span data-ttu-id="643e6-119">例 2</span><span class="sxs-lookup"><span data-stu-id="643e6-119">Example 2</span></span>

<span data-ttu-id="643e6-120">この例では、現在の場所を RegFunction スタックにプッシュし、現在の場所を場所に変更し `HKLM:\Software\Policies` ます。</span><span class="sxs-lookup"><span data-stu-id="643e6-120">This example pushes the current location onto the RegFunction stack and changes the current location to the `HKLM:\Software\Policies` location.</span></span>

```
PS C:\> Push-Location HKLM:\Software\Policies -StackName RegFunction
```

<span data-ttu-id="643e6-121">Location コマンドレットは、任意の PowerShell ドライブ (PSDrive) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="643e6-121">You can use the Location cmdlets in any PowerShell drive (PSDrive).</span></span>

### <span data-ttu-id="643e6-122">例 3</span><span class="sxs-lookup"><span data-stu-id="643e6-122">Example 3</span></span>

<span data-ttu-id="643e6-123">このコマンドを実行すると、現在の場所が既定のスタックにプッシュされます。</span><span class="sxs-lookup"><span data-stu-id="643e6-123">This command pushes the current location onto the default stack.</span></span> <span data-ttu-id="643e6-124">場所は変更されません。</span><span class="sxs-lookup"><span data-stu-id="643e6-124">It does not change the location.</span></span>

```
PS C:\> Push-Location
```

### <span data-ttu-id="643e6-125">例 4-名前付きスタックを作成して使用する</span><span class="sxs-lookup"><span data-stu-id="643e6-125">Example 4 - Create and use a named stack</span></span>

<span data-ttu-id="643e6-126">これらのコマンドは、名前付き場所スタックを作成および使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="643e6-126">These commands show how to create and use a named location stack.</span></span>

```
PS C:\> Push-Location ~ -StackName Stack2
PS C:\Users\User01> Pop-Location -StackName Stack2
PS C:\>
```

<span data-ttu-id="643e6-127">最初のコマンドは、現在の場所を Stack2 という名前の新しいスタックにプッシュした後、現在の場所を、コマンドでチルダ記号 () によって表されるホームディレクトリに変更し `~` ます。このディレクトリは、ファイルシステムプロバイダーのドライブで使用された場合、 `$HOME` とと同等です `$env:USERPROFILE` 。</span><span class="sxs-lookup"><span data-stu-id="643e6-127">The first command pushes the current location onto a new stack named Stack2, and then changes the current location to the home directory, represented in the command by the tilde symbol (`~`), which when used on a FileSystem provider drives is equivalent to `$HOME` and `$env:USERPROFILE`.</span></span>

<span data-ttu-id="643e6-128">Stack2 がセッションに存在しない場合は、に `Push-Location` よって作成されます。</span><span class="sxs-lookup"><span data-stu-id="643e6-128">If Stack2 does not already exist in the session, `Push-Location` creates it.</span></span> <span data-ttu-id="643e6-129">2番目のコマンドは、コマンドレットを使用して、 `Pop-Location` Stack2 スタックから元の場所 () をポップし `C:\` ます。</span><span class="sxs-lookup"><span data-stu-id="643e6-129">The second command uses the `Pop-Location` cmdlet to pop the original location (`C:\`) from the Stack2 stack.</span></span> <span data-ttu-id="643e6-130">**Stackname** パラメーターを指定しないと、は名前のない `Pop-Location` 既定のスタックから場所をポップします。</span><span class="sxs-lookup"><span data-stu-id="643e6-130">Without the **StackName** parameter, `Pop-Location` would pop the location from the unnamed default stack.</span></span>

<span data-ttu-id="643e6-131">場所スタックの詳細については、「 [注](#notes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="643e6-131">For more information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="643e6-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="643e6-132">PARAMETERS</span></span>

### <span data-ttu-id="643e6-133">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="643e6-133">-LiteralPath</span></span>

<span data-ttu-id="643e6-134">新しい場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="643e6-134">Specifies the path to the new location.</span></span> <span data-ttu-id="643e6-135">**Path** パラメーターと異なり、 **LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="643e6-135">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="643e6-136">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="643e6-136">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="643e6-137">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="643e6-137">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="643e6-138">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="643e6-138">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="643e6-139">-PassThru</span><span class="sxs-lookup"><span data-stu-id="643e6-139">-PassThru</span></span>

<span data-ttu-id="643e6-140">場所を表すオブジェクトをパイプラインに渡します。</span><span class="sxs-lookup"><span data-stu-id="643e6-140">Passes an object representing the location to the pipeline.</span></span> <span data-ttu-id="643e6-141">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="643e6-141">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="643e6-142">-Path</span><span class="sxs-lookup"><span data-stu-id="643e6-142">-Path</span></span>

<span data-ttu-id="643e6-143">現在の場所をスタックの最上部に追加 (プッシュ) してから、このパスが示す場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="643e6-143">Changes your location to the location specified by this path after it adds (pushes) the current location onto the top of the stack.</span></span> <span data-ttu-id="643e6-144">このコマンドレットをサポートするプロバイダーの任意のパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="643e6-144">Enter a path to any location whose provider supports this cmdlet.</span></span> <span data-ttu-id="643e6-145">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="643e6-145">Wildcards are permitted.</span></span> <span data-ttu-id="643e6-146">パラメーター名は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="643e6-146">The parameter name is optional.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="643e6-147">-StackName</span><span class="sxs-lookup"><span data-stu-id="643e6-147">-StackName</span></span>

<span data-ttu-id="643e6-148">現在の場所を追加する場所スタックを指定します。</span><span class="sxs-lookup"><span data-stu-id="643e6-148">Specifies the location stack to which the current location is added.</span></span> <span data-ttu-id="643e6-149">場所スタック名を入力します。</span><span class="sxs-lookup"><span data-stu-id="643e6-149">Enter a location stack name.</span></span>
<span data-ttu-id="643e6-150">スタックが存在しない場合は、に `Push-Location` よって作成されます。</span><span class="sxs-lookup"><span data-stu-id="643e6-150">If the stack does not exist, `Push-Location` creates it.</span></span>

<span data-ttu-id="643e6-151">このパラメーターを指定しない場合、は `Push-Location` 現在の場所スタックに場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="643e6-151">Without this parameter, `Push-Location` adds the location to the current location stack.</span></span> <span data-ttu-id="643e6-152">既定では、現在の場所スタックは、PowerShell によって作成される名前のない既定の場所スタックです。</span><span class="sxs-lookup"><span data-stu-id="643e6-152">By default, the current location stack is the unnamed default location stack that PowerShell creates.</span></span>
<span data-ttu-id="643e6-153">場所スタックを現在の場所スタックにするには、コマンドレットの **Stackname** パラメーターを使用し `Set-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="643e6-153">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span> <span data-ttu-id="643e6-154">場所スタックの詳細については、「 [注](#notes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="643e6-154">For more information about location stacks, see the [Notes](#notes).</span></span>

> [!NOTE]
> <span data-ttu-id="643e6-155">`Push-Location` 現在の場所スタックでない限り、名前のない既定のスタックに場所を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="643e6-155">`Push-Location` cannot add a location to the unnamed default stack unless it is the current location stack.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Default stack
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="643e6-156">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="643e6-156">-UseTransaction</span></span>

<span data-ttu-id="643e6-157">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="643e6-157">Includes the command in the active transaction.</span></span> <span data-ttu-id="643e6-158">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="643e6-158">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="643e6-159">詳細については、「[about_Transactions](../Microsoft.PowerShell.Core/About/about_transactions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="643e6-159">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_transactions.md).</span></span>

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

### <span data-ttu-id="643e6-160">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="643e6-160">CommonParameters</span></span>

<span data-ttu-id="643e6-161">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="643e6-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="643e6-162">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="643e6-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="643e6-163">入力</span><span class="sxs-lookup"><span data-stu-id="643e6-163">INPUTS</span></span>

### <span data-ttu-id="643e6-164">System.String</span><span class="sxs-lookup"><span data-stu-id="643e6-164">System.String</span></span>

<span data-ttu-id="643e6-165">パイプを使用してパス (リテラルパスではない) を含む文字列をにパイプすることができ `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="643e6-165">You can pipe a string that contains a path (but not a literal path) to `Push-Location`.</span></span>

## <span data-ttu-id="643e6-166">出力</span><span class="sxs-lookup"><span data-stu-id="643e6-166">OUTPUTS</span></span>

### <span data-ttu-id="643e6-167">なしまたはシステムの管理. PathInfo</span><span class="sxs-lookup"><span data-stu-id="643e6-167">None or System.Management.Automation.PathInfo</span></span>

<span data-ttu-id="643e6-168">**PassThru** パラメーターを使用すると、によって、 `Push-Location` 場所を表す system.string オブジェクトが生成さ **れます。**</span><span class="sxs-lookup"><span data-stu-id="643e6-168">When you use the **PassThru** parameter, `Push-Location` generates a **System.Management.Automation.PathInfo** object that represents the location.</span></span> <span data-ttu-id="643e6-169">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="643e6-169">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="643e6-170">注</span><span class="sxs-lookup"><span data-stu-id="643e6-170">NOTES</span></span>

<span data-ttu-id="643e6-171">PowerShell では、プロセスごとに複数の実行空間がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="643e6-171">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="643e6-172">各実行空間には、独自の _現在のディレクトリ_ があります。</span><span class="sxs-lookup"><span data-stu-id="643e6-172">Each runspace has its own _current directory_.</span></span>
<span data-ttu-id="643e6-173">これはと同じではありません `[System.Environment]::CurrentDirectory` 。</span><span class="sxs-lookup"><span data-stu-id="643e6-173">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="643e6-174">この動作は、明示的なディレクトリパスを指定せずに、.NET Api を呼び出したり、ネイティブアプリケーションを実行したりするときに問題になることがあります。</span><span class="sxs-lookup"><span data-stu-id="643e6-174">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="643e6-175">場所のコマンドレットでプロセス全体の現在のディレクトリが設定されていても、別の実行空間によっていつでも変更される可能性があるため、このディレクトリに依存することはできません。</span><span class="sxs-lookup"><span data-stu-id="643e6-175">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="643e6-176">現在の実行空間に固有の現在の作業ディレクトリを使用して、パスベースの操作を実行するには、location コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="643e6-176">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="643e6-177">スタックとは、最後に追加された項目のみがアクセス可能な後入れ先出しリストです。</span><span class="sxs-lookup"><span data-stu-id="643e6-177">A stack is a last-in, first-out list in which only the most recently added item is accessible.</span></span>
<span data-ttu-id="643e6-178">使用した順序でスタックに項目を追加し、その後、逆の順序で使用するために項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="643e6-178">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="643e6-179">PowerShell では、プロバイダーの場所を場所スタックに格納できます。</span><span class="sxs-lookup"><span data-stu-id="643e6-179">PowerShell lets you store provider locations in location stacks.</span></span>

<span data-ttu-id="643e6-180">PowerShell では、名前のない既定の場所スタックが作成され、複数の名前付きロケーションスタックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="643e6-180">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="643e6-181">スタック名を指定しない場合、PowerShell は現在の場所スタックを使用します。</span><span class="sxs-lookup"><span data-stu-id="643e6-181">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="643e6-182">既定では、名前のない既定の場所は現在の場所スタックですが、コマンドレットを使用して `Set-Location` 現在の場所スタックを変更できます。</span><span class="sxs-lookup"><span data-stu-id="643e6-182">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="643e6-183">場所スタックを管理するには、次のように PowerShell Location コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="643e6-183">To manage location stacks, use the PowerShell Location cmdlets, as follows.</span></span>

- <span data-ttu-id="643e6-184">場所スタックに場所を追加するには、コマンドレットを使用し `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="643e6-184">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="643e6-185">場所スタックから場所を取得するには、コマンドレットを使用し `Pop-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="643e6-185">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="643e6-186">現在の場所スタック内の場所を表示するには、コマンドレットの **stack** パラメーターを使用し `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="643e6-186">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="643e6-187">名前付きの場所スタック内の場所を表示するには、コマンドレットの **Stackname** パラメーターを使用し `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="643e6-187">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="643e6-188">新しい場所スタックを作成するには、コマンドレットの StackName パラメーターを使用し `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="643e6-188">To create a new location stack, use the StackName parameter of the `Push-Location` cmdlet.</span></span> <span data-ttu-id="643e6-189">存在しないスタックを指定すると、によっ `Push-Location` てスタックが作成されます。</span><span class="sxs-lookup"><span data-stu-id="643e6-189">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="643e6-190">場所スタックを現在の場所スタックにするには、コマンドレットの StackName パラメーターを使用し `Set-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="643e6-190">To make a location stack the current location stack, use the StackName parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="643e6-191">名前のない既定の場所スタックは、現在の場所スタックになっている場合にだけ、完全にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="643e6-191">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="643e6-192">名前付きの場所スタックを現在の場所スタックにすると、またはコマンドレットを使用して `Push-Location` `Pop-Location` 既定のスタックから項目を追加または取得したり、コマンドレットを使用して名前のないスタック内の場所を表示したりすることができなくなり `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="643e6-192">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="643e6-193">名前のないスタックを現在のスタックにするには、コマンドレットの **Stackname** パラメーター `Set-Location` の値を `$null` または空の文字列 () に設定し `""` ます。</span><span class="sxs-lookup"><span data-stu-id="643e6-193">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="643e6-194">また、組み込みエイリアスであるを参照することもでき `Push-Location` `pushd` ます。</span><span class="sxs-lookup"><span data-stu-id="643e6-194">You can also refer to `Push-Location` by its built-in alias, `pushd`.</span></span> <span data-ttu-id="643e6-195">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="643e6-195">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="643e6-196">`Push-Location`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="643e6-196">The `Push-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="643e6-197">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="643e6-197">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="643e6-198">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="643e6-198">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="643e6-199">関連リンク</span><span class="sxs-lookup"><span data-stu-id="643e6-199">RELATED LINKS</span></span>

[<span data-ttu-id="643e6-200">Get-Location</span><span class="sxs-lookup"><span data-stu-id="643e6-200">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="643e6-201">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="643e6-201">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="643e6-202">Set-Location</span><span class="sxs-lookup"><span data-stu-id="643e6-202">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="643e6-203">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="643e6-203">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="643e6-204">about_Providers</span><span class="sxs-lookup"><span data-stu-id="643e6-204">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
