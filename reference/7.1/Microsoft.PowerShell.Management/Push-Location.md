---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/push-location?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Push-Location
ms.openlocfilehash: 91ee85507d8ad0f128025af3d549d461310a415d
ms.sourcegitcommit: 01a1c253f48b61c943f6d6aca4e603118014015f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "93219152"
---
# <span data-ttu-id="61f32-103">Push-Location</span><span class="sxs-lookup"><span data-stu-id="61f32-103">Push-Location</span></span>

## <span data-ttu-id="61f32-104">概要</span><span class="sxs-lookup"><span data-stu-id="61f32-104">SYNOPSIS</span></span>
<span data-ttu-id="61f32-105">現在の場所を、場所スタックの最上部に追加します。</span><span class="sxs-lookup"><span data-stu-id="61f32-105">Adds the current location to the top of a location stack.</span></span>

## <span data-ttu-id="61f32-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="61f32-106">SYNTAX</span></span>

### <span data-ttu-id="61f32-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="61f32-107">Path (Default)</span></span>

```
Push-Location [[-Path] <String>] [-PassThru] [-StackName <String>] [<CommonParameters>]
```

### <span data-ttu-id="61f32-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="61f32-108">LiteralPath</span></span>

```
Push-Location [-LiteralPath <String>] [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## <span data-ttu-id="61f32-109">Description</span><span class="sxs-lookup"><span data-stu-id="61f32-109">DESCRIPTION</span></span>

<span data-ttu-id="61f32-110">`Push-Location`コマンドレットは、現在の場所を場所スタックに追加 ("プッシュ") します。</span><span class="sxs-lookup"><span data-stu-id="61f32-110">The `Push-Location` cmdlet adds ("pushes") the current location onto a location stack.</span></span> <span data-ttu-id="61f32-111">パスを指定すると、は `Push-Location` 現在の場所を場所スタックにプッシュし、現在の場所をパスで指定された場所に変更します。</span><span class="sxs-lookup"><span data-stu-id="61f32-111">If you specify a path, `Push-Location` pushes the current location onto a location stack and then changes the current location to the location specified by the path.</span></span> <span data-ttu-id="61f32-112">コマンドレットを使用して `Pop-Location` 、場所スタックから場所を取得できます。</span><span class="sxs-lookup"><span data-stu-id="61f32-112">You can use the `Pop-Location` cmdlet to get locations from the location stack.</span></span>

<span data-ttu-id="61f32-113">既定では、コマンドレットは現在の場所を `Push-Location` 現在の場所スタックにプッシュしますが、 **stackname** パラメーターを使用して別の場所スタックを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="61f32-113">By default, the `Push-Location` cmdlet pushes the current location onto the current location stack, but you can use the **StackName** parameter to specify an alternate location stack.</span></span> <span data-ttu-id="61f32-114">スタックが存在しない場合は、に `Push-Location` よって作成されます。</span><span class="sxs-lookup"><span data-stu-id="61f32-114">If the stack does not exist, `Push-Location` creates it.</span></span>

<span data-ttu-id="61f32-115">場所スタックの詳細については、「 [注](#notes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61f32-115">For more information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="61f32-116">例</span><span class="sxs-lookup"><span data-stu-id="61f32-116">EXAMPLES</span></span>

### <span data-ttu-id="61f32-117">例 1</span><span class="sxs-lookup"><span data-stu-id="61f32-117">Example 1</span></span>

<span data-ttu-id="61f32-118">この例では、現在の場所を既定の場所スタックにプッシュし、その場所をに変更し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="61f32-118">This example pushes the current location onto the default location stack and then changes the location to `C:\Windows`.</span></span>

```
PS C:\> Push-Location C:\Windows
```

### <span data-ttu-id="61f32-119">例 2</span><span class="sxs-lookup"><span data-stu-id="61f32-119">Example 2</span></span>

<span data-ttu-id="61f32-120">この例では、現在の場所を RegFunction スタックにプッシュし、現在の場所を場所に変更し `HKLM:\Software\Policies` ます。</span><span class="sxs-lookup"><span data-stu-id="61f32-120">This example pushes the current location onto the RegFunction stack and changes the current location to the `HKLM:\Software\Policies` location.</span></span>

```
PS C:\> Push-Location HKLM:\Software\Policies -StackName RegFunction
```

<span data-ttu-id="61f32-121">Location コマンドレットは、任意の PowerShell ドライブ (PSDrive) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="61f32-121">You can use the Location cmdlets in any PowerShell drive (PSDrive).</span></span>

### <span data-ttu-id="61f32-122">例 3</span><span class="sxs-lookup"><span data-stu-id="61f32-122">Example 3</span></span>

<span data-ttu-id="61f32-123">このコマンドを実行すると、現在の場所が既定のスタックにプッシュされます。</span><span class="sxs-lookup"><span data-stu-id="61f32-123">This command pushes the current location onto the default stack.</span></span> <span data-ttu-id="61f32-124">場所は変更されません。</span><span class="sxs-lookup"><span data-stu-id="61f32-124">It does not change the location.</span></span>

```
PS C:\> Push-Location
```

### <span data-ttu-id="61f32-125">例 4-名前付きスタックを作成して使用する</span><span class="sxs-lookup"><span data-stu-id="61f32-125">Example 4 - Create and use a named stack</span></span>

<span data-ttu-id="61f32-126">これらのコマンドは、名前付き場所スタックを作成および使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="61f32-126">These commands show how to create and use a named location stack.</span></span>

```
PS C:\> Push-Location ~ -StackName Stack2
PS C:\Users\User01> Pop-Location -StackName Stack2
PS C:\>
```

<span data-ttu-id="61f32-127">最初のコマンドは、現在の場所を Stack2 という名前の新しいスタックにプッシュした後、現在の場所を、コマンドでチルダ記号 () によって表されるホームディレクトリに変更し `~` ます。このディレクトリは、ファイルシステムプロバイダーのドライブで使用された場合、 `$HOME` とと同等です `$env:USERPROFILE` 。</span><span class="sxs-lookup"><span data-stu-id="61f32-127">The first command pushes the current location onto a new stack named Stack2, and then changes the current location to the home directory, represented in the command by the tilde symbol (`~`), which when used on a FileSystem provider drives is equivalent to `$HOME` and `$env:USERPROFILE`.</span></span>

<span data-ttu-id="61f32-128">Stack2 がセッションに存在しない場合は、に `Push-Location` よって作成されます。</span><span class="sxs-lookup"><span data-stu-id="61f32-128">If Stack2 does not already exist in the session, `Push-Location` creates it.</span></span> <span data-ttu-id="61f32-129">2番目のコマンドは、コマンドレットを使用して、 `Pop-Location` Stack2 スタックから元の場所 () をポップし `C:\` ます。</span><span class="sxs-lookup"><span data-stu-id="61f32-129">The second command uses the `Pop-Location` cmdlet to pop the original location (`C:\`) from the Stack2 stack.</span></span> <span data-ttu-id="61f32-130">**Stackname** パラメーターを指定しないと、は名前のない `Pop-Location` 既定のスタックから場所をポップします。</span><span class="sxs-lookup"><span data-stu-id="61f32-130">Without the **StackName** parameter, `Pop-Location` would pop the location from the unnamed default stack.</span></span>

<span data-ttu-id="61f32-131">場所スタックの詳細については、「 [注](#notes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61f32-131">For more information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="61f32-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="61f32-132">PARAMETERS</span></span>

### <span data-ttu-id="61f32-133">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="61f32-133">-LiteralPath</span></span>

<span data-ttu-id="61f32-134">新しい場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="61f32-134">Specifies the path to the new location.</span></span> <span data-ttu-id="61f32-135">**Path** パラメーターと異なり、 **LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="61f32-135">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="61f32-136">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="61f32-136">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="61f32-137">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="61f32-137">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="61f32-138">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="61f32-138">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="61f32-139">-PassThru</span><span class="sxs-lookup"><span data-stu-id="61f32-139">-PassThru</span></span>

<span data-ttu-id="61f32-140">場所を表すオブジェクトをパイプラインに渡します。</span><span class="sxs-lookup"><span data-stu-id="61f32-140">Passes an object representing the location to the pipeline.</span></span> <span data-ttu-id="61f32-141">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="61f32-141">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="61f32-142">-Path</span><span class="sxs-lookup"><span data-stu-id="61f32-142">-Path</span></span>

<span data-ttu-id="61f32-143">現在の場所をスタックの最上部に追加 (プッシュ) してから、このパスが示す場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="61f32-143">Changes your location to the location specified by this path after it adds (pushes) the current location onto the top of the stack.</span></span> <span data-ttu-id="61f32-144">このコマンドレットをサポートするプロバイダーの任意のパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="61f32-144">Enter a path to any location whose provider supports this cmdlet.</span></span> <span data-ttu-id="61f32-145">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="61f32-145">Wildcards are permitted.</span></span> <span data-ttu-id="61f32-146">パラメーター名は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="61f32-146">The parameter name is optional.</span></span>

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

### <span data-ttu-id="61f32-147">-StackName</span><span class="sxs-lookup"><span data-stu-id="61f32-147">-StackName</span></span>

<span data-ttu-id="61f32-148">現在の場所を追加する場所スタックを指定します。</span><span class="sxs-lookup"><span data-stu-id="61f32-148">Specifies the location stack to which the current location is added.</span></span> <span data-ttu-id="61f32-149">場所スタック名を入力します。</span><span class="sxs-lookup"><span data-stu-id="61f32-149">Enter a location stack name.</span></span>
<span data-ttu-id="61f32-150">スタックが存在しない場合は、に `Push-Location` よって作成されます。</span><span class="sxs-lookup"><span data-stu-id="61f32-150">If the stack does not exist, `Push-Location` creates it.</span></span>

<span data-ttu-id="61f32-151">このパラメーターを指定しない場合、は `Push-Location` 現在の場所スタックに場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="61f32-151">Without this parameter, `Push-Location` adds the location to the current location stack.</span></span> <span data-ttu-id="61f32-152">既定では、現在の場所スタックは、PowerShell によって作成される名前のない既定の場所スタックです。</span><span class="sxs-lookup"><span data-stu-id="61f32-152">By default, the current location stack is the unnamed default location stack that PowerShell creates.</span></span>
<span data-ttu-id="61f32-153">場所スタックを現在の場所スタックにするには、コマンドレットの **Stackname** パラメーターを使用し `Set-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="61f32-153">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span> <span data-ttu-id="61f32-154">場所スタックの詳細については、「 [注](#notes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61f32-154">For more information about location stacks, see the [Notes](#notes).</span></span>

> [!NOTE]
> <span data-ttu-id="61f32-155">`Push-Location` 現在の場所スタックでない限り、名前のない既定のスタックに場所を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="61f32-155">`Push-Location` cannot add a location to the unnamed default stack unless it is the current location stack.</span></span>

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

### <span data-ttu-id="61f32-156">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="61f32-156">CommonParameters</span></span>

<span data-ttu-id="61f32-157">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="61f32-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="61f32-158">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61f32-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="61f32-159">入力</span><span class="sxs-lookup"><span data-stu-id="61f32-159">INPUTS</span></span>

### <span data-ttu-id="61f32-160">System.String</span><span class="sxs-lookup"><span data-stu-id="61f32-160">System.String</span></span>

<span data-ttu-id="61f32-161">パイプを使用してパス (リテラルパスではない) を含む文字列をにパイプすることができ `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="61f32-161">You can pipe a string that contains a path (but not a literal path) to `Push-Location`.</span></span>

## <span data-ttu-id="61f32-162">出力</span><span class="sxs-lookup"><span data-stu-id="61f32-162">OUTPUTS</span></span>

### <span data-ttu-id="61f32-163">なしまたはシステムの管理. PathInfo</span><span class="sxs-lookup"><span data-stu-id="61f32-163">None or System.Management.Automation.PathInfo</span></span>

<span data-ttu-id="61f32-164">**PassThru** パラメーターを使用すると、によって、 `Push-Location` 場所を表す system.string オブジェクトが生成さ **れます。**</span><span class="sxs-lookup"><span data-stu-id="61f32-164">When you use the **PassThru** parameter, `Push-Location` generates a **System.Management.Automation.PathInfo** object that represents the location.</span></span> <span data-ttu-id="61f32-165">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="61f32-165">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="61f32-166">注</span><span class="sxs-lookup"><span data-stu-id="61f32-166">NOTES</span></span>

<span data-ttu-id="61f32-167">PowerShell では、プロセスごとに複数の実行空間がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="61f32-167">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="61f32-168">各実行空間には、独自の _現在のディレクトリ_ があります。</span><span class="sxs-lookup"><span data-stu-id="61f32-168">Each runspace has its own _current directory_.</span></span>
<span data-ttu-id="61f32-169">これはと同じではありません `[System.Environment]::CurrentDirectory` 。</span><span class="sxs-lookup"><span data-stu-id="61f32-169">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="61f32-170">この動作は、明示的なディレクトリパスを指定せずに、.NET Api を呼び出したり、ネイティブアプリケーションを実行したりするときに問題になることがあります。</span><span class="sxs-lookup"><span data-stu-id="61f32-170">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="61f32-171">場所のコマンドレットでプロセス全体の現在のディレクトリが設定されていても、別の実行空間によっていつでも変更される可能性があるため、このディレクトリに依存することはできません。</span><span class="sxs-lookup"><span data-stu-id="61f32-171">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="61f32-172">現在の実行空間に固有の現在の作業ディレクトリを使用して、パスベースの操作を実行するには、location コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61f32-172">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="61f32-173">スタックとは、最後に追加された項目のみがアクセス可能な後入れ先出しリストです。</span><span class="sxs-lookup"><span data-stu-id="61f32-173">A stack is a last-in, first-out list in which only the most recently added item is accessible.</span></span>
<span data-ttu-id="61f32-174">使用した順序でスタックに項目を追加し、その後、逆の順序で使用するために項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="61f32-174">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="61f32-175">PowerShell では、プロバイダーの場所を場所スタックに格納できます。</span><span class="sxs-lookup"><span data-stu-id="61f32-175">PowerShell lets you store provider locations in location stacks.</span></span>

<span data-ttu-id="61f32-176">PowerShell では、名前のない既定の場所スタックが作成され、複数の名前付きロケーションスタックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="61f32-176">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="61f32-177">スタック名を指定しない場合、PowerShell は現在の場所スタックを使用します。</span><span class="sxs-lookup"><span data-stu-id="61f32-177">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="61f32-178">既定では、名前のない既定の場所は現在の場所スタックですが、コマンドレットを使用して `Set-Location` 現在の場所スタックを変更できます。</span><span class="sxs-lookup"><span data-stu-id="61f32-178">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="61f32-179">場所スタックを管理するには、次のように PowerShell Location コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="61f32-179">To manage location stacks, use the PowerShell Location cmdlets, as follows.</span></span>

- <span data-ttu-id="61f32-180">場所スタックに場所を追加するには、コマンドレットを使用し `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="61f32-180">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="61f32-181">場所スタックから場所を取得するには、コマンドレットを使用し `Pop-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="61f32-181">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="61f32-182">現在の場所スタック内の場所を表示するには、コマンドレットの **stack** パラメーターを使用し `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="61f32-182">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="61f32-183">名前付きの場所スタック内の場所を表示するには、コマンドレットの **Stackname** パラメーターを使用し `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="61f32-183">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="61f32-184">新しい場所スタックを作成するには、コマンドレットの StackName パラメーターを使用し `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="61f32-184">To create a new location stack, use the StackName parameter of the `Push-Location` cmdlet.</span></span> <span data-ttu-id="61f32-185">存在しないスタックを指定すると、によっ `Push-Location` てスタックが作成されます。</span><span class="sxs-lookup"><span data-stu-id="61f32-185">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="61f32-186">場所スタックを現在の場所スタックにするには、コマンドレットの StackName パラメーターを使用し `Set-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="61f32-186">To make a location stack the current location stack, use the StackName parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="61f32-187">名前のない既定の場所スタックは、現在の場所スタックになっている場合にだけ、完全にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="61f32-187">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="61f32-188">名前付きの場所スタックを現在の場所スタックにすると、またはコマンドレットを使用して `Push-Location` `Pop-Location` 既定のスタックから項目を追加または取得したり、コマンドレットを使用して名前のないスタック内の場所を表示したりすることができなくなり `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="61f32-188">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="61f32-189">名前のないスタックを現在のスタックにするには、コマンドレットの **Stackname** パラメーター `Set-Location` の値を `$null` または空の文字列 () に設定し `""` ます。</span><span class="sxs-lookup"><span data-stu-id="61f32-189">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="61f32-190">また、組み込みエイリアスであるを参照することもでき `Push-Location` `pushd` ます。</span><span class="sxs-lookup"><span data-stu-id="61f32-190">You can also refer to `Push-Location` by its built-in alias, `pushd`.</span></span> <span data-ttu-id="61f32-191">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61f32-191">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="61f32-192">`Push-Location`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="61f32-192">The `Push-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="61f32-193">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="61f32-193">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="61f32-194">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61f32-194">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="61f32-195">関連リンク</span><span class="sxs-lookup"><span data-stu-id="61f32-195">RELATED LINKS</span></span>

[<span data-ttu-id="61f32-196">Get-Location</span><span class="sxs-lookup"><span data-stu-id="61f32-196">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="61f32-197">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="61f32-197">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="61f32-198">Set-Location</span><span class="sxs-lookup"><span data-stu-id="61f32-198">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="61f32-199">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="61f32-199">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="61f32-200">about_Providers</span><span class="sxs-lookup"><span data-stu-id="61f32-200">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
