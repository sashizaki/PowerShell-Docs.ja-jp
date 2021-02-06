---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/push-location?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Push-Location
ms.openlocfilehash: eaa7622e29680de4228579f8b77a6c829a586bf8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601223"
---
# <span data-ttu-id="f0097-102">Push-Location</span><span class="sxs-lookup"><span data-stu-id="f0097-102">Push-Location</span></span>

## <span data-ttu-id="f0097-103">概要</span><span class="sxs-lookup"><span data-stu-id="f0097-103">SYNOPSIS</span></span>
<span data-ttu-id="f0097-104">現在の場所を、場所スタックの最上部に追加します。</span><span class="sxs-lookup"><span data-stu-id="f0097-104">Adds the current location to the top of a location stack.</span></span>

## <span data-ttu-id="f0097-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f0097-105">SYNTAX</span></span>

### <span data-ttu-id="f0097-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="f0097-106">Path (Default)</span></span>

```
Push-Location [[-Path] <String>] [-PassThru] [-StackName <String>] [<CommonParameters>]
```

### <span data-ttu-id="f0097-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f0097-107">LiteralPath</span></span>

```
Push-Location [-LiteralPath <String>] [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## <span data-ttu-id="f0097-108">Description</span><span class="sxs-lookup"><span data-stu-id="f0097-108">DESCRIPTION</span></span>

<span data-ttu-id="f0097-109">`Push-Location`コマンドレットは、現在の場所を場所スタックに追加 ("プッシュ") します。</span><span class="sxs-lookup"><span data-stu-id="f0097-109">The `Push-Location` cmdlet adds ("pushes") the current location onto a location stack.</span></span> <span data-ttu-id="f0097-110">パスを指定すると、は `Push-Location` 現在の場所を場所スタックにプッシュし、現在の場所をパスで指定された場所に変更します。</span><span class="sxs-lookup"><span data-stu-id="f0097-110">If you specify a path, `Push-Location` pushes the current location onto a location stack and then changes the current location to the location specified by the path.</span></span> <span data-ttu-id="f0097-111">コマンドレットを使用して `Pop-Location` 、場所スタックから場所を取得できます。</span><span class="sxs-lookup"><span data-stu-id="f0097-111">You can use the `Pop-Location` cmdlet to get locations from the location stack.</span></span>

<span data-ttu-id="f0097-112">既定では、コマンドレットは現在の場所を `Push-Location` 現在の場所スタックにプッシュしますが、 **stackname** パラメーターを使用して別の場所スタックを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0097-112">By default, the `Push-Location` cmdlet pushes the current location onto the current location stack, but you can use the **StackName** parameter to specify an alternate location stack.</span></span> <span data-ttu-id="f0097-113">スタックが存在しない場合は、に `Push-Location` よって作成されます。</span><span class="sxs-lookup"><span data-stu-id="f0097-113">If the stack does not exist, `Push-Location` creates it.</span></span>

<span data-ttu-id="f0097-114">場所スタックの詳細については、「 [注](#notes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0097-114">For more information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="f0097-115">例</span><span class="sxs-lookup"><span data-stu-id="f0097-115">EXAMPLES</span></span>

### <span data-ttu-id="f0097-116">例 1</span><span class="sxs-lookup"><span data-stu-id="f0097-116">Example 1</span></span>

<span data-ttu-id="f0097-117">この例では、現在の場所を既定の場所スタックにプッシュし、その場所をに変更し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="f0097-117">This example pushes the current location onto the default location stack and then changes the location to `C:\Windows`.</span></span>

```
PS C:\> Push-Location C:\Windows
```

### <span data-ttu-id="f0097-118">例 2</span><span class="sxs-lookup"><span data-stu-id="f0097-118">Example 2</span></span>

<span data-ttu-id="f0097-119">この例では、現在の場所を RegFunction スタックにプッシュし、現在の場所を場所に変更し `HKLM:\Software\Policies` ます。</span><span class="sxs-lookup"><span data-stu-id="f0097-119">This example pushes the current location onto the RegFunction stack and changes the current location to the `HKLM:\Software\Policies` location.</span></span>

```
PS C:\> Push-Location HKLM:\Software\Policies -StackName RegFunction
```

<span data-ttu-id="f0097-120">Location コマンドレットは、任意の PowerShell ドライブ (PSDrive) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0097-120">You can use the Location cmdlets in any PowerShell drive (PSDrive).</span></span>

### <span data-ttu-id="f0097-121">例 3</span><span class="sxs-lookup"><span data-stu-id="f0097-121">Example 3</span></span>

<span data-ttu-id="f0097-122">このコマンドを実行すると、現在の場所が既定のスタックにプッシュされます。</span><span class="sxs-lookup"><span data-stu-id="f0097-122">This command pushes the current location onto the default stack.</span></span> <span data-ttu-id="f0097-123">場所は変更されません。</span><span class="sxs-lookup"><span data-stu-id="f0097-123">It does not change the location.</span></span>

```
PS C:\> Push-Location
```

### <span data-ttu-id="f0097-124">例 4-名前付きスタックを作成して使用する</span><span class="sxs-lookup"><span data-stu-id="f0097-124">Example 4 - Create and use a named stack</span></span>

<span data-ttu-id="f0097-125">これらのコマンドは、名前付き場所スタックを作成および使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f0097-125">These commands show how to create and use a named location stack.</span></span>

```
PS C:\> Push-Location ~ -StackName Stack2
PS C:\Users\User01> Pop-Location -StackName Stack2
PS C:\>
```

<span data-ttu-id="f0097-126">最初のコマンドは、現在の場所を Stack2 という名前の新しいスタックにプッシュした後、現在の場所を、コマンドでチルダ記号 () によって表されるホームディレクトリに変更し `~` ます。このディレクトリは、ファイルシステムプロバイダーのドライブで使用された場合、 `$HOME` とと同等です `$env:USERPROFILE` 。</span><span class="sxs-lookup"><span data-stu-id="f0097-126">The first command pushes the current location onto a new stack named Stack2, and then changes the current location to the home directory, represented in the command by the tilde symbol (`~`), which when used on a FileSystem provider drives is equivalent to `$HOME` and `$env:USERPROFILE`.</span></span>

<span data-ttu-id="f0097-127">Stack2 がセッションに存在しない場合は、に `Push-Location` よって作成されます。</span><span class="sxs-lookup"><span data-stu-id="f0097-127">If Stack2 does not already exist in the session, `Push-Location` creates it.</span></span> <span data-ttu-id="f0097-128">2番目のコマンドは、コマンドレットを使用して、 `Pop-Location` Stack2 スタックから元の場所 () をポップし `C:\` ます。</span><span class="sxs-lookup"><span data-stu-id="f0097-128">The second command uses the `Pop-Location` cmdlet to pop the original location (`C:\`) from the Stack2 stack.</span></span> <span data-ttu-id="f0097-129">**Stackname** パラメーターを指定しないと、は名前のない `Pop-Location` 既定のスタックから場所をポップします。</span><span class="sxs-lookup"><span data-stu-id="f0097-129">Without the **StackName** parameter, `Pop-Location` would pop the location from the unnamed default stack.</span></span>

<span data-ttu-id="f0097-130">場所スタックの詳細については、「 [注](#notes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0097-130">For more information about location stacks, see the [Notes](#notes).</span></span>

## <span data-ttu-id="f0097-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f0097-131">PARAMETERS</span></span>

### <span data-ttu-id="f0097-132">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f0097-132">-LiteralPath</span></span>

<span data-ttu-id="f0097-133">新しい場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0097-133">Specifies the path to the new location.</span></span> <span data-ttu-id="f0097-134">**Path** パラメーターと異なり、**LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0097-134">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="f0097-135">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="f0097-135">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="f0097-136">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="f0097-136">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="f0097-137">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="f0097-137">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="f0097-138">-PassThru</span><span class="sxs-lookup"><span data-stu-id="f0097-138">-PassThru</span></span>

<span data-ttu-id="f0097-139">場所を表すオブジェクトをパイプラインに渡します。</span><span class="sxs-lookup"><span data-stu-id="f0097-139">Passes an object representing the location to the pipeline.</span></span> <span data-ttu-id="f0097-140">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="f0097-140">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="f0097-141">-Path</span><span class="sxs-lookup"><span data-stu-id="f0097-141">-Path</span></span>

<span data-ttu-id="f0097-142">現在の場所をスタックの最上部に追加 (プッシュ) してから、このパスが示す場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="f0097-142">Changes your location to the location specified by this path after it adds (pushes) the current location onto the top of the stack.</span></span> <span data-ttu-id="f0097-143">このコマンドレットをサポートするプロバイダーの任意のパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="f0097-143">Enter a path to any location whose provider supports this cmdlet.</span></span> <span data-ttu-id="f0097-144">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0097-144">Wildcards are permitted.</span></span> <span data-ttu-id="f0097-145">パラメーター名は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="f0097-145">The parameter name is optional.</span></span>

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

### <span data-ttu-id="f0097-146">-StackName</span><span class="sxs-lookup"><span data-stu-id="f0097-146">-StackName</span></span>

<span data-ttu-id="f0097-147">現在の場所を追加する場所スタックを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0097-147">Specifies the location stack to which the current location is added.</span></span> <span data-ttu-id="f0097-148">場所スタック名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f0097-148">Enter a location stack name.</span></span>
<span data-ttu-id="f0097-149">スタックが存在しない場合は、に `Push-Location` よって作成されます。</span><span class="sxs-lookup"><span data-stu-id="f0097-149">If the stack does not exist, `Push-Location` creates it.</span></span>

<span data-ttu-id="f0097-150">このパラメーターを指定しない場合、は `Push-Location` 現在の場所スタックに場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="f0097-150">Without this parameter, `Push-Location` adds the location to the current location stack.</span></span> <span data-ttu-id="f0097-151">既定では、現在の場所スタックは、PowerShell によって作成される名前のない既定の場所スタックです。</span><span class="sxs-lookup"><span data-stu-id="f0097-151">By default, the current location stack is the unnamed default location stack that PowerShell creates.</span></span>
<span data-ttu-id="f0097-152">場所スタックを現在の場所スタックにするには、コマンドレットの **Stackname** パラメーターを使用し `Set-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="f0097-152">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span> <span data-ttu-id="f0097-153">場所スタックの詳細については、「 [注](#notes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0097-153">For more information about location stacks, see the [Notes](#notes).</span></span>

> [!NOTE]
> <span data-ttu-id="f0097-154">`Push-Location` 現在の場所スタックでない限り、名前のない既定のスタックに場所を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="f0097-154">`Push-Location` cannot add a location to the unnamed default stack unless it is the current location stack.</span></span>

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

### <span data-ttu-id="f0097-155">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f0097-155">CommonParameters</span></span>

<span data-ttu-id="f0097-156">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f0097-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f0097-157">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0097-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f0097-158">入力</span><span class="sxs-lookup"><span data-stu-id="f0097-158">INPUTS</span></span>

### <span data-ttu-id="f0097-159">System.String</span><span class="sxs-lookup"><span data-stu-id="f0097-159">System.String</span></span>

<span data-ttu-id="f0097-160">パイプを使用してパス (リテラルパスではない) を含む文字列をにパイプすることができ `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="f0097-160">You can pipe a string that contains a path (but not a literal path) to `Push-Location`.</span></span>

## <span data-ttu-id="f0097-161">出力</span><span class="sxs-lookup"><span data-stu-id="f0097-161">OUTPUTS</span></span>

### <span data-ttu-id="f0097-162">なしまたはシステムの管理. PathInfo</span><span class="sxs-lookup"><span data-stu-id="f0097-162">None or System.Management.Automation.PathInfo</span></span>

<span data-ttu-id="f0097-163">**PassThru** パラメーターを使用すると、によって、 `Push-Location` 場所を表す system.string オブジェクトが生成さ **れます。**</span><span class="sxs-lookup"><span data-stu-id="f0097-163">When you use the **PassThru** parameter, `Push-Location` generates a **System.Management.Automation.PathInfo** object that represents the location.</span></span> <span data-ttu-id="f0097-164">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="f0097-164">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f0097-165">注</span><span class="sxs-lookup"><span data-stu-id="f0097-165">NOTES</span></span>

<span data-ttu-id="f0097-166">PowerShell では、プロセスごとに複数の実行空間がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f0097-166">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="f0097-167">各実行空間には、独自の _現在のディレクトリ_ があります。</span><span class="sxs-lookup"><span data-stu-id="f0097-167">Each runspace has its own _current directory_.</span></span>
<span data-ttu-id="f0097-168">これはと同じではありません `[System.Environment]::CurrentDirectory` 。</span><span class="sxs-lookup"><span data-stu-id="f0097-168">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="f0097-169">この動作は、明示的なディレクトリパスを指定せずに、.NET Api を呼び出したり、ネイティブアプリケーションを実行したりするときに問題になることがあります。</span><span class="sxs-lookup"><span data-stu-id="f0097-169">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="f0097-170">場所のコマンドレットでプロセス全体の現在のディレクトリが設定されていても、別の実行空間によっていつでも変更される可能性があるため、このディレクトリに依存することはできません。</span><span class="sxs-lookup"><span data-stu-id="f0097-170">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="f0097-171">現在の実行空間に固有の現在の作業ディレクトリを使用して、パスベースの操作を実行するには、location コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0097-171">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="f0097-172">スタックとは、最後に追加された項目のみがアクセス可能な後入れ先出しリストです。</span><span class="sxs-lookup"><span data-stu-id="f0097-172">A stack is a last-in, first-out list in which only the most recently added item is accessible.</span></span>
<span data-ttu-id="f0097-173">使用した順序でスタックに項目を追加し、その後、逆の順序で使用するために項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="f0097-173">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="f0097-174">PowerShell では、プロバイダーの場所を場所スタックに格納できます。</span><span class="sxs-lookup"><span data-stu-id="f0097-174">PowerShell lets you store provider locations in location stacks.</span></span>

<span data-ttu-id="f0097-175">PowerShell では、名前のない既定の場所スタックが作成され、複数の名前付きロケーションスタックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f0097-175">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="f0097-176">スタック名を指定しない場合、PowerShell は現在の場所スタックを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0097-176">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="f0097-177">既定では、名前のない既定の場所は現在の場所スタックですが、コマンドレットを使用して `Set-Location` 現在の場所スタックを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f0097-177">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="f0097-178">場所スタックを管理するには、次のように PowerShell Location コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0097-178">To manage location stacks, use the PowerShell Location cmdlets, as follows.</span></span>

- <span data-ttu-id="f0097-179">場所スタックに場所を追加するには、コマンドレットを使用し `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="f0097-179">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="f0097-180">場所スタックから場所を取得するには、コマンドレットを使用し `Pop-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="f0097-180">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="f0097-181">現在の場所スタック内の場所を表示するには、コマンドレットの **stack** パラメーターを使用し `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="f0097-181">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="f0097-182">名前付きの場所スタック内の場所を表示するには、コマンドレットの **Stackname** パラメーターを使用し `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="f0097-182">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="f0097-183">新しい場所スタックを作成するには、コマンドレットの StackName パラメーターを使用し `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="f0097-183">To create a new location stack, use the StackName parameter of the `Push-Location` cmdlet.</span></span> <span data-ttu-id="f0097-184">存在しないスタックを指定すると、によっ `Push-Location` てスタックが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f0097-184">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="f0097-185">場所スタックを現在の場所スタックにするには、コマンドレットの StackName パラメーターを使用し `Set-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="f0097-185">To make a location stack the current location stack, use the StackName parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="f0097-186">名前のない既定の場所スタックは、現在の場所スタックになっている場合にだけ、完全にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f0097-186">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="f0097-187">名前付きの場所スタックを現在の場所スタックにすると、またはコマンドレットを使用して `Push-Location` `Pop-Location` 既定のスタックから項目を追加または取得したり、コマンドレットを使用して名前のないスタック内の場所を表示したりすることができなくなり `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="f0097-187">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="f0097-188">名前のないスタックを現在のスタックにするには、コマンドレットの **Stackname** パラメーター `Set-Location` の値を `$null` または空の文字列 () に設定し `""` ます。</span><span class="sxs-lookup"><span data-stu-id="f0097-188">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

<span data-ttu-id="f0097-189">また、組み込みエイリアスであるを参照することもでき `Push-Location` `pushd` ます。</span><span class="sxs-lookup"><span data-stu-id="f0097-189">You can also refer to `Push-Location` by its built-in alias, `pushd`.</span></span> <span data-ttu-id="f0097-190">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0097-190">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="f0097-191">`Push-Location`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="f0097-191">The `Push-Location` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="f0097-192">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="f0097-192">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="f0097-193">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0097-193">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="f0097-194">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f0097-194">RELATED LINKS</span></span>

[<span data-ttu-id="f0097-195">Get-Location</span><span class="sxs-lookup"><span data-stu-id="f0097-195">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="f0097-196">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="f0097-196">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="f0097-197">Set-Location</span><span class="sxs-lookup"><span data-stu-id="f0097-197">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="f0097-198">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="f0097-198">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="f0097-199">about_Providers</span><span class="sxs-lookup"><span data-stu-id="f0097-199">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
