---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Module
ms.openlocfilehash: a1052c357f19fd8f06eb39a14f8e8eded0c881a9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212787"
---
# <span data-ttu-id="64773-103">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="64773-103">Remove-Module</span></span>

## <span data-ttu-id="64773-104">概要</span><span class="sxs-lookup"><span data-stu-id="64773-104">SYNOPSIS</span></span>
<span data-ttu-id="64773-105">現在のセッションからモジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="64773-105">Removes modules from the current session.</span></span>

## <span data-ttu-id="64773-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="64773-106">SYNTAX</span></span>

### <span data-ttu-id="64773-107">name</span><span class="sxs-lookup"><span data-stu-id="64773-107">name</span></span>

```
Remove-Module [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="64773-108">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="64773-108">FullyQualifiedName</span></span>

```
Remove-Module [-FullyQualifiedName] <ModuleSpecification[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="64773-109">ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="64773-109">ModuleInfo</span></span>

```
Remove-Module [-ModuleInfo] <PSModuleInfo[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="64773-110">Description</span><span class="sxs-lookup"><span data-stu-id="64773-110">DESCRIPTION</span></span>

<span data-ttu-id="64773-111">**Remove-Module** コマンドレットは、現在のセッションから、コマンドレットと関数などのモジュールのメンバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="64773-111">The **Remove-Module** cmdlet removes the members of a module, such as cmdlets and functions, from the current session.</span></span>

<span data-ttu-id="64773-112">モジュールにアセンブリ (.dll) が含まれる場合は、アセンブリによって実装されているすべてのメンバーが削除されますが、アセンブリはアンロードされません。</span><span class="sxs-lookup"><span data-stu-id="64773-112">If the module includes an assembly (.dll), all members that are implemented by the assembly are removed, but the assembly is not unloaded.</span></span>

<span data-ttu-id="64773-113">このコマンドレットは、コンピューターからモジュールをアンインストール、または削除しません。</span><span class="sxs-lookup"><span data-stu-id="64773-113">This cmdlet does not uninstall the module or delete it from the computer.</span></span>
<span data-ttu-id="64773-114">現在の PowerShell セッションにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="64773-114">It affects only the current PowerShell session.</span></span>

## <span data-ttu-id="64773-115">例</span><span class="sxs-lookup"><span data-stu-id="64773-115">EXAMPLES</span></span>

### <span data-ttu-id="64773-116">例 1: モジュールを削除する</span><span class="sxs-lookup"><span data-stu-id="64773-116">Example 1: Remove a module</span></span>

```powershell
Remove-Module -Name "BitsTransfer"
```

<span data-ttu-id="64773-117">このコマンドは、現在のセッションから BitsTransfer モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="64773-117">This command removes the BitsTransfer module from the current session.</span></span>

### <span data-ttu-id="64773-118">例 2: すべてのモジュールを削除する</span><span class="sxs-lookup"><span data-stu-id="64773-118">Example 2: Remove all modules</span></span>

```powershell
Get-Module | Remove-Module
```

<span data-ttu-id="64773-119">このコマンドは、現在のセッションからすべてのモジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="64773-119">This command removes all modules from the current session.</span></span>

### <span data-ttu-id="64773-120">例 3: パイプラインを使用してモジュールを削除する</span><span class="sxs-lookup"><span data-stu-id="64773-120">Example 3: Remove modules by using the pipeline</span></span>

```powershell
"FileTransfer", "PSDiagnostics" | Remove-Module -Verbose
```

```Output
VERBOSE: Performing operation "Remove-Module" on Target "filetransfer (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\filetransfer\filetransfer.psd1')".
VERBOSE: Performing operation "Remove-Module" on Target "Microsoft.BackgroundIntelligentTransfer.Management (Path: 'C:\Windows\assembly\GAC_MSIL\Microsoft.BackgroundIntelligentTransfer.Management\1.0.0.0__31bf3856ad364e35\Microsoft.BackgroundIntelligentTransfe
r.Management.dll')".
VERBOSE: Performing operation "Remove-Module" on Target "psdiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\psdiagnostics.psd1')".
VERBOSE: Removing imported function 'Start-Trace'.
VERBOSE: Removing imported function 'Stop-Trace'.
VERBOSE: Removing imported function 'Enable-WSManTrace'.
VERBOSE: Removing imported function 'Disable-WSManTrace'.
VERBOSE: Removing imported function 'Enable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Disable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Set-LogProperties'.
VERBOSE: Removing imported function 'Get-LogProperties'.
VERBOSE: Removing imported function 'Enable-PSTrace'.
VERBOSE: Removing imported function 'Disable-PSTrace'.
VERBOSE: Performing operation "Remove-Module" on Target "PSDiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\PSDiagnostics.psm1')".
```

<span data-ttu-id="64773-121">このコマンドは、現在のセッションから BitsTransfer モジュールと PSDiagnostics モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="64773-121">This command removes the BitsTransfer and PSDiagnostics modules from the current session.</span></span>

<span data-ttu-id="64773-122">このコマンドは、パイプライン演算子 (|) を使用してモジュール名を **Remove-Module** に送信します。</span><span class="sxs-lookup"><span data-stu-id="64773-122">The command uses a pipeline operator (|) to send the module names to **Remove-Module** .</span></span>
<span data-ttu-id="64773-123">*Verbose* 共通パラメーターを使用して、削除されるメンバーに関する詳細な情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="64773-123">It uses the *Verbose* common parameter to get detailed information about the members that are removed.</span></span>

<span data-ttu-id="64773-124">*詳細* メッセージには、削除された項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="64773-124">The *Verbose* messages show the items that are removed.</span></span>
<span data-ttu-id="64773-125">BitsTransfer モジュールには、コマンドレットを実装するアセンブリ、および独自のアセンブリを含む入れ子になったモジュールが含まれるため、これらのメッセージは異なります。</span><span class="sxs-lookup"><span data-stu-id="64773-125">The messages differ because the BitsTransfer module includes an assembly that implements its cmdlets and a nested module with its own assembly.</span></span>
<span data-ttu-id="64773-126">PSDiagnostics モジュールには、関数をエクスポートするモジュール スクリプト ファイル (.psm1) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="64773-126">The PSDiagnostics module includes a module script file (.psm1) that exports functions.</span></span>

### <span data-ttu-id="64773-127">例 4: ModuleInfo を使用してモジュールを削除する</span><span class="sxs-lookup"><span data-stu-id="64773-127">Example 4: Remove a module by using ModuleInfo</span></span>

```powershell
$a = Get-Module BitsTransfer
Remove-Module -ModuleInfo $a
```

<span data-ttu-id="64773-128">このコマンドは、 *Moduleinfo* パラメーターを使用して BitsTransfer モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="64773-128">This command uses the *ModuleInfo* parameter to remove the BitsTransfer module.</span></span>

## <span data-ttu-id="64773-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="64773-129">PARAMETERS</span></span>

### <span data-ttu-id="64773-130">-Force</span><span class="sxs-lookup"><span data-stu-id="64773-130">-Force</span></span>

<span data-ttu-id="64773-131">このコマンドレットが読み取り専用モジュールを削除することを示します。</span><span class="sxs-lookup"><span data-stu-id="64773-131">Indicates that this cmdlet removes read-only modules.</span></span>
<span data-ttu-id="64773-132">既定では、 **Remove-Module** は、読み取り/書き込みモジュールのみ削除します。</span><span class="sxs-lookup"><span data-stu-id="64773-132">By default, **Remove-Module** removes only read-write modules.</span></span>

<span data-ttu-id="64773-133">**ReadOnly** 値と **ReadWrite** 値は、モジュールの **AccessMode** プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="64773-133">The **ReadOnly** and **ReadWrite** values are stored in **AccessMode** property of a module.</span></span>

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

### <span data-ttu-id="64773-134">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="64773-134">-FullyQualifiedName</span></span>

<span data-ttu-id="64773-135">削除するモジュールの完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="64773-135">Specifies the fully qualified names of modules to remove.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="64773-136">-ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="64773-136">-ModuleInfo</span></span>

<span data-ttu-id="64773-137">削除するモジュール オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="64773-137">Specifies the module objects to remove.</span></span>
<span data-ttu-id="64773-138">モジュールオブジェクト ( **PSModuleInfo** ) を含む変数、または Get-Module コマンドなどのモジュールオブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="64773-138">Enter a variable that contains a module object ( **PSModuleInfo** ) or a command that gets a module object, such as a Get-Module command.</span></span>
<span data-ttu-id="64773-139">パイプを使用してモジュール オブジェクトを **Remove-Module** に渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="64773-139">You can also pipe module objects to **Remove-Module** .</span></span>

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="64773-140">-Name</span><span class="sxs-lookup"><span data-stu-id="64773-140">-Name</span></span>

<span data-ttu-id="64773-141">削除するモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="64773-141">Specifies the names of modules to remove.</span></span>
<span data-ttu-id="64773-142">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="64773-142">Wildcard characters are permitted.</span></span>
<span data-ttu-id="64773-143">パイプを使用して名前の文字列を **Remove-Module** に渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="64773-143">You can also pipe name strings to **Remove-Module** .</span></span>

```yaml
Type: System.String[]
Parameter Sets: name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="64773-144">-Confirm</span><span class="sxs-lookup"><span data-stu-id="64773-144">-Confirm</span></span>

<span data-ttu-id="64773-145">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="64773-145">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64773-146">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="64773-146">-WhatIf</span></span>

<span data-ttu-id="64773-147">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="64773-147">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="64773-148">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="64773-148">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64773-149">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="64773-149">CommonParameters</span></span>

<span data-ttu-id="64773-150">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="64773-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="64773-151">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64773-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="64773-152">入力</span><span class="sxs-lookup"><span data-stu-id="64773-152">INPUTS</span></span>

### <span data-ttu-id="64773-153">System.string, PSModuleInfo のようになります。</span><span class="sxs-lookup"><span data-stu-id="64773-153">System.String, System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="64773-154">パイプを使用してモジュール名とモジュールオブジェクトを削除し、モジュールを **削除** することができます。</span><span class="sxs-lookup"><span data-stu-id="64773-154">You can pipe module names and module objects to **Remove-Module** .</span></span>

## <span data-ttu-id="64773-155">出力</span><span class="sxs-lookup"><span data-stu-id="64773-155">OUTPUTS</span></span>

### <span data-ttu-id="64773-156">なし</span><span class="sxs-lookup"><span data-stu-id="64773-156">None</span></span>

<span data-ttu-id="64773-157">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="64773-157">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="64773-158">注</span><span class="sxs-lookup"><span data-stu-id="64773-158">NOTES</span></span>

## <span data-ttu-id="64773-159">関連リンク</span><span class="sxs-lookup"><span data-stu-id="64773-159">RELATED LINKS</span></span>

[<span data-ttu-id="64773-160">Get-Module</span><span class="sxs-lookup"><span data-stu-id="64773-160">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="64773-161">Import-Module</span><span class="sxs-lookup"><span data-stu-id="64773-161">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="64773-162">about_Modules</span><span class="sxs-lookup"><span data-stu-id="64773-162">about_Modules</span></span>](About/about_Modules.md)
